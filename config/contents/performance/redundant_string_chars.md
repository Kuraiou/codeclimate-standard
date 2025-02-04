This cop checks for redundant `String#chars`.

### Example:
    # bad
    str.chars[0..2]
    str.chars.slice(0..2)

    # good
    str[0..2].chars

    # bad
    str.chars.first
    str.chars.first(2)

    # good
    str[0]
    str[0...2].chars

    # bad
    str.chars.take(2)
    str.chars.length
    str.chars.size
    str.chars.empty?

    # good
    str[0...2].chars
    str.length
    str.size
    str.empty?

    # For example, if the receiver is a blank string, it will be incompatible.
    # If a negative value is specified for the receiver, `nil` is returned.
    str.chars.last    # Incompatible with `str[-1]`.
    str.chars.last(2) # Incompatible with `str[-2..-1].chars`.
    str.chars.drop(2) # Incompatible with `str[2..-1].chars`.
