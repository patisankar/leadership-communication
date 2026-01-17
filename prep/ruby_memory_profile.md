```ruby
# gc_profile_demo.rb
# Run: ruby gc_profile_demo.rb
#
# Optional (recommended): run with GC stats enabled
#   RUBYOPT="--enable-gems" ruby gc_profile_demo.rb

require "json"
require "objspace"

# ---------- Workload (intentionally allocation-heavy) ----------
def workload(n: 200_000)
  total = 0

  n.times do |i|
    # Common real-world pattern: build payload + serialize + parse
    payload = {
      "id" => i.to_s,                # allocates new string each time
      "name" => "user_" + i.to_s,    # allocates multiple strings
      "tags" => %w[a b c].map { |t| t + i.to_s } # allocates arrays + strings
    }

    json = JSON.generate(payload)    # allocations
    parsed = JSON.parse(json)        # allocations

    total += parsed["id"].to_i
  end

  total
end

# ---------- Measurement helpers ----------
def snapshot_gc(label)
  s = GC.stat
  c = ObjectSpace.count_objects

  puts "\n=== #{label} ==="
  puts "GC.stat: count=#{s[:count]}, minor=#{s[:minor_gc_count]}, major=#{s[:major_gc_count]}"
  puts "        total_allocated_objects=#{s[:total_allocated_objects]}"
  puts "        heap_live_slots=#{s[:heap_live_slots]}, heap_free_slots=#{s[:heap_free_slots]}"
  puts "Objects: TOTAL=#{c[:TOTAL]}, T_STRING=#{c[:T_STRING]}, T_ARRAY=#{c[:T_ARRAY]}, T_HASH=#{c[:T_HASH]}"
end

GC::Profiler.enable

snapshot_gc("BEFORE")

t0 = Process.clock_gettime(Process::CLOCK_MONOTONIC)
result = workload
t1 = Process.clock_gettime(Process::CLOCK_MONOTONIC)

snapshot_gc("AFTER")

puts "\nResult: #{result}"
puts format("Elapsed: %.3fs", (t1 - t0))

puts "\n--- GC::Profiler (top lines) ---"
report = GC::Profiler.result
puts report.lines.first(20).join
puts "(... truncated; full report length=#{report.lines.size} lines)"
