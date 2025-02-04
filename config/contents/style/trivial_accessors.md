This cop looks for trivial reader/writer methods, that could
have been created with the attr_* family of functions automatically.

### Example:
    # bad
    def foo
      @foo
    end

    def bar=(val)
      @bar = val
    end

    def self.baz
      @baz
    end

    # good
    attr_reader :foo
    attr_writer :bar

    class << self
      attr_reader :baz
    end

### Example: ExactNameMatch: true (default)
    # good
    def name
      @other_name
    end

### Example: ExactNameMatch: false
    # bad
    def name
      @other_name
    end

### Example: AllowPredicates: true (default)
    # good
    def foo?
      @foo
    end

### Example: AllowPredicates: false
    # bad
    def foo?
      @foo
    end

    # good
    attr_reader :foo

### Example: AllowDSLWriters: true (default)
    # good
    def on_exception(action)
      @on_exception=action
    end

### Example: AllowDSLWriters: false
    # bad
    def on_exception(action)
      @on_exception=action
    end

    # good
    attr_writer :on_exception

### Example: IgnoreClassMethods: false (default)
    # bad
    def self.foo
      @foo
    end

    # good
    class << self
      attr_reader :foo
    end

### Example: IgnoreClassMethods: true
    # good
    def self.foo
      @foo
    end

### Example: AllowedMethods: ['allowed_method']
    # good
    def allowed_method
      @foo
    end