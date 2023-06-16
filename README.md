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
