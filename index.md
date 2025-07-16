---
title: "Microsoft\_Learn - Exercices de présentation de l’IA dans Azure"
permalink: index.html
layout: home
---

# AI-900 : Exercices de Présentation de l’IA dans Azure

Ces exercices pratiques sont conçus pour accompagner le contenu des formations sur [Microsoft Learn](https://docs.microsoft.com/training/).

Pour effectuer ces exercices, vous devez disposer d’un abonnement Microsoft Azure. Vous pouvez vous inscrire à un essai gratuit sur [https://azure.microsoft.com](https://azure.microsoft.com).

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
| Exercices |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
