This cop identifies places where numeric argument to BigDecimal should be
converted to string. Initializing from String is faster
than from Numeric for BigDecimal.

### Example:
    # bad
    BigDecimal(1, 2)
    BigDecimal(1.2, 3, exception: true)

    # good
    BigDecimal('1', 2)
    BigDecimal('1.2', 3, exception: true)
