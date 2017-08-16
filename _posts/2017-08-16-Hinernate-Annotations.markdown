---
layout: post
title:  Hibernate annotations use
date:   2017-08-16 18:16
description: march & april, looking forward to summer
---

To add named foreign key in hibernate you should annotate your fields with some like this:

{% highlight java %}
    @ManyToMany(cascade = CascadeType.ALL)
        @JoinTable(name = "user_role",
                joinColumns = @JoinColumn(name = "user_id",
                foreignKey = @ForeignKey(name = "fk_users_id")),
                inverseJoinColumns = @JoinColumn(name = "role_id",
                foreignKey = @ForeignKey(name = "fk_roles_id")))
        private Set<Role> roles;
{% endhighlight %}

In foreignKey annotation you simple addend a name to the table link.

Good luck and Happy Coding!