```ruby
def toasterTypeBgColor(toasterType)
    case toasterType
    when "info"
      'bg-blue-500'
    when "warning"
      'bg-yellow-500'
    when "error"
      'bg-red-500'
    else
      "bg-white"
    end
end

def toasterTypeTitle(toasterType)
  case toasterType
  when "info"
    'Info Alert'
  when "warning"
    'Warning Alert'
  when "error"
    'Error Alert'
  else
    "Alert"
  end
end
```
