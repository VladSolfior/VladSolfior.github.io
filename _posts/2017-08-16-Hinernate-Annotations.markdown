---
layout: post
title:  Hibernate named @ForeignKey annotation
date:   2017-08-16 18:16
description: Hibernate generated value foreign key solution
---

When you work in Hibernate you sometimes see the <code>UK_3u5h7y36qqa13y3mauc5xxayq</code> ...

<div class="img_row">
	<img class="col three" src="/img/name.png">
</div>
<div class="container">
    To solution's this situation you should add a named foreign key annotation.
    Try annotate fields with some like this:

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
</div>