+++
comments = true
image = ""
title = "With pattern in Ruby"
author = ""
share = true
menu = ""
date = "2017-03-20"
draft = false

+++

I have been using lately this nitty gritty pattern mostly inspired by Ember's [with template helper](http://emberjs.com/api/classes/Ember.Templates.helpers.html#method_with).
If you have an object (usually in your .erb template) which has a long diameter
it becomes a bit problematic when you have to repeat it again and again.
<!--more-->

For instance (imagine these in one line with some HTML):

```ruby
<%= @presenter.unit.department.name %>
<%= @presenter.unit.department.year %>
<%= @presenter.unit.department.faculty.count %>
```

What you can do is to assign a variable in the template and use that variable instead.
Personally I don't like assigning stuff in the templates so instead I like doing the same using a `with` helper:

```ruby
  def with(object)
    yield object
  end
```

Now you can do:

```ruby
<% with(@presenter.unit.department) do |dep| %>
  <%= dep.name %>
  <%= dep.year %>
  <%= dep.faculty.count %>
<% end %>
```
That now even fits in one line.

```ruby
<% with(@presenter.unit.department) do |dep| %>
  <%= dep.name %> <%= dep.year %> <%= dep.faculty.count %>
<% end %>
```

Usually long diameters is not the best thing to have, but when you do have them
this little thing could help you make your code more beautiful :)
