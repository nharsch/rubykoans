
## Objects

* `Nil` is n object

* assertmatch takes unquoted patterns like this:
assert_match `/substring/` "testring"

* `nil.to_s == ""` but `nil.inspect == "nil"`

* objects have unique ids

* object IDs for small ints are fixed, are == 2 * int + 1

## Arrays

* appending `my_array << new item`

* slices are [start_index, **length**]

* out of range array indexes return `nil`: `[1,2,3][4] == nil`

* **ranges** 
  inclusive : `(1..4).to_a == [1,2,3,4 ]`
  exclusive : `(1...4).to_a == [1,2,3]` 

* array push and pop : like python append and pop

* **shift** and **unshift**:
    a = [2]
    a.push 3
    => [2,3]
    a.unshift 1
    => [1,2,3]
    b = a.shift
    a == [2,3]
    b == 1

### Array assignment

    a,b = [1,2]
    a == 1
    b == 2
    a,b == [1,2,3]
    a == 1
    b == 2
    a,*b = [1,2,3] 
    a == 1
    b == [2,3]

# Hashes

    a = {:one => 'uno', :two => 'dos'}
    a[:one]
    =>'uno'
    a[:three]
    =>nil
    a.fetch(:one)
    =>'uno'
    a.fetch(:three)
    KeyError: key not found: :two
    
  * `hash.merge(another_hash)` returns new hash, doesn't mutate hash or another_hash 
  
  * **default values**
    a = Hash.new('def')
    a[:nope]
    => "def"

  * tricky
    h = Hash.new([])

    hash[:one] << "uno"
    hash[:two] << "dos"

    hash[:one]
     => ["uno","dos"]
    hash[:two]
     => ["uno","dos"]
