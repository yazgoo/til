# prod articles

Some nuggets in that one:

https://engineering.contentsquare.com/2021/ten-flink-gotchas/

## Comuting paralellism

```ruby
require 'prettyprint'
#
# https://engineering.contentsquare.com/2021/ten-flink-gotchas/
#    public static int computeOperatorIndexForKeyGroup(
#            int maxParallelism, int parallelism, int keyGroupId) {
#        return keyGroupId * parallelism / maxParallelism;
#    }
#  maxParallelism, which is set to operatorParallelism + (operatorParallelism / 2)
#
#

def comupute_operator_index_for_key_group(parallelism, key_group_id, max_parallelism = nil) 
  max_parallelism ||= parallelism + (parallelism / 2)
  key_group_id * parallelism / max_parallelism 
end

res = {}
# parallelism = 120
parallelism = 60 
(0...120*2).to_a.each do |i|
    operator_index = comupute_operator_index_for_key_group(parallelism, i) % parallelism
    res[operator_index] ||= 0
    res[operator_index] += 1
end
pp res
```
