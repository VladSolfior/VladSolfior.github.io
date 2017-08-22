---
layout: post
title: Interface vs Абстрактный класс: различия
date: 2017-08-22 18:09:00
description: Interface vs Абстрактный класс: различия
---
<div class="container">

    <p>Разница между интерфейсом и абстрактным классом:</p>
    <div class="row">
        <div class="img_row">
                	<img class="img-responsive" src="/img/interface.png">
        </div>
    </div>

    <div class="row">
        {% highlight java %}
        public interface Test {
            public default void def() {
                System.out.println("inside default method");
            }

            public int toImpl();

            int i = 0;
            Object r = null;
            Object d = new Object();
        }

        public class TestImpl implements Test {
            @Override
            public int toImpl() {
                return 0;
            }

            {
                Object d1 = Test.d;
                Object r1 = Test.r;
                int i = Test.i;

                this.toImpl();
                this.def();
            }
        }

        <br>

        public abstract class Test {
            public void def() {
                System.out.println("inside default method");
            }

            public abstract int toImpl();

            int i = 0;
            Object r = null;
            Object d = new Object();
        }

        public class TestImpl extends Test {
            @Override
            public int toImpl() {
                return 0;
            }

            {
            Object d1 = super.d;
            Object r1 = super.r;
            int i = super.i;

            this.toImpl();
            super.def();
            }
        }



        {% endhighlight %}
    </div>

</div>