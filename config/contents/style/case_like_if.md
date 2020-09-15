This cop identifies places where `if-elsif` constructions
can be replaced with `case-when`.

### Example:
    # bad
    if status == :active
      perform_action
    elsif status == :inactive || status == :hibernating
      check_timeout
    else
      final_action
    end

    # good
    case status
    when :active
      perform_action
    when :inactive, :hibernating
      check_timeout
    else
      final_action
    end
