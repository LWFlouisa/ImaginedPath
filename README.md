# ImaginedPath
A way to imagine a story branch that doesn't exist.

## Theorized Methodology
~~~ruby
# If in branch 1 is the tragic path.
# And in branch 3 is the best ending you can get.
# Then hallucinate a fictive pathway for branch 2.

row = 0

# Make sure that story elements are kept on seperate lines.
branch_1 = File.readlines("_narratives/pathways/branch1.txt")
branch_3 = File.readlines("_narratives/pathways/branch3.txt")

# Make the total imagined branch the size of the darkest path.
branch_size = branch_1.size.to_i

# Imagined a compromise path that is neither ideal or tragic.
open("_imaginedpath/pathways/branch2.txt", "w") { |f|
  branch_size.times do
    segment_1 = branch_1[row]
    segment_2 = brench_2[row]

    f.puts "#{segment_1} #{segment_1}"

    row = row + 1
  end
}
~~~

## For More Accurate Prediction
~~~ruby
# [ Charlotte Dies ] [     Charlotte Lives ]
# [   Dates Player ] [ Doesn't Date Player ]

charlotte_row = [0, 1]
dating_row    = [0, 1]

# Make sure that story elements are kept on seperate lines.
charlotte_fate = File.readlines("_narratives/outcomes/charlotte_fate.txt")
dating_outcome = File.readlines("_narratives/outcomes/dating_outcomes.txt")

# Make the total imagined branch the size of the darkest path.
branch_size = branch_1.size.to_i

# Imagined a compromise path that is neither ideal or tragic.
open("_imaginedpath/pathways/nuetral_outcome.txt", "w") { |f|
  actual_nuetral_outcome = File.read("_narrative/expected_nuetral/nuetral_ending.txt") # [ Charlotte Lives ] [ Doesn't Date Player ]

  branch_size.times
    segment_1 = charlotte_fate[charlotte_row].strip
    segment_2 = dating_outcome[dating_row].strip

    nuetral_outcome = "#{segment_1} #{segment_2}"

    if nuetral_outcome == actual_nuetral_outcome
      f.puts nuetral_outcome
    else
      puts "Skipping outcome as this ending is established..."
    end

    charlotte_row = charlotte_row.sample 
    dating_row    = dating_row.sample
  end
}
~~~

## For Best Prediction
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
