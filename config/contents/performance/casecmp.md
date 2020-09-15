This cop identifies places where a case-insensitive string comparison
can better be implemented using `casecmp`.
This cop is unsafe because `String#casecmp` and `String#casecmp?` behave
differently when using Non-ASCII characters.

### Example:
    # bad
    str.downcase == 'abc'
    str.upcase.eql? 'ABC'
    'abc' == str.downcase
    'ABC'.eql? str.upcase
    str.downcase == str.downcase

    # good
    str.casecmp('ABC').zero?
    'abc'.casecmp(str).zero?