# ImaginedPath
A way to imagine a story branch that doesn't exist.

~~~ruby
charlotte_row = [0, 1]
dating_row    = [0, 1]

# Make sure that story elements are kept on seperate lines.
charlotte_fate = File.readlines("_narratives/outcomes/charlotte_fate.txt")
dating_outcome = File.readlines("_narratives/outcomes/dating_outcomes.txt")

# Make the total imagined branch the size of the darkest path.
# branch_size = branch_1.size.to_i

# Imagined a compromise path that is neither ideal or tragic.
open("_imaginedpath/outcomes/nuetral_outcome.txt", "w") { |f|
  segment_1 = charlotte_fate[0].strip
  segment_2 = dating_outcome[1].strip

  f.puts "#{segment_1} #{segment_2}"
}
~~~

## Spontaneous Prolog Conditional Creation
Proof of concept for how to use it for creating new prolog conditionals.

[Conditional Creation In Prolog](https://github.com/LWFlouisa/IProlog)


## Exponential Complexity
Simply by adding one more ruleset, you end up with a situation where the amount of new conditionals created outnumbers the original things the programmaer anticipated.

~~~
# 0 Charlotte Dies            0 Never Dates Player
# 1 Charlotte Fate Unknown    1 Relationship Is Unknown
# 2 Charlotte Lives           2 Dates Player
~~~

~~~ Collumnar Ruleset
A 0 1 2   1 2 0
B 2 0 1   2 0 1
C 1 2 0   0 1 2
~~~

~~~ Total Results
Charlotte Dies, Relationship Is Unknown
Charlotte Fate Unknown, Dates Player
Charlotte Lives, Never Dates Player
Charlotte Lives, Dates Player
Charlotte Dies, Never Dates Player
Charlotte Fate Unknown, Relationship Is Unknown
Charlotte Fate Unknown, Never Dates Player
Charlotte Lives, Relationship Is Unknown
Charlotte Dies, Dates Player
~~~
