---
title: Test
layout: default
permalink: test.html
---

<html>

    <head>

        <style>

            * {
              box-sizing: border-box;
            }

            .row::after {
                content: "";
                clear: both;
                display: table;
            }

            [class*="col-"] {
            float: center;
            padding: 10% 50%;
            }

            html {
                font-family: "Lucida Sans", sans-serif;
            }

            .header {
                background:url('{{ site.baseurl }}/_assets/images/home/travis-grossen.jpg'); 
                padding: 50px;
                background-position: center;
                background-repeat: no-repeat;
                background-size: cover;
                color: #ffffff;
                }

            .col-1 {width: 100%;}

        </style>

    </head>

    <body>

        <div class="header">
	    <h1 style="text-align:center;">{{ page.title }}</h1>
        </div>

        <div class="col-1">
	 
            <ul>
            {% for post in site.posts %}
                <li>
                    <a href="{{ post.url }}">{{ post.title}}</a>
                </li>
            {% endfor %}
            </ul>

        </div>