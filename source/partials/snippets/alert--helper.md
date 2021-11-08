``` ruby
  def flashTypeIcon(flashType)
    case flashType
    when "info"
      '<img src="/assets/info.png" alt="">'
    when "warning"
      '<img src="/assets/warn.png" alt="">'
    when "error"
      '<img src="/assets/cancel.png" alt="">'
    else
      ""
    end
  end

  def flashTypeBgColor(flashType)
    case flashType
    when "info"
      'bg-blue-200 border-2 border-blue-500'
    when "warning"
      'bg-yellow-200 border-2 border-yellow-500'
    when "error"
      'bg-red-200 border-2 border-red-500'
    else
      "bg-white"
    end
  end
```
