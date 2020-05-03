---
title: "Présentation du SEO"
date: 2020-03-26
header:
  image: /assets/images/webaroo-seo.jpg
categories:
  - talk
tags: 
  - SEO
  - référencement
  - french
---

Dans le cadre de la formation à la Wild Code School, nous pouvons assister à des talks pour découvrir l'univers du numérique et mieux appréhender la place des développeurs dans cet écosystème. 

Le premier talk auquel j'ai assisté consiste en une présentation du *Search Engine Optimization* faite par Maxence Marius, consultant SEO spécialisé banque et prêt-à-porter.

Cette présentation était très riche en enseignements. Je vais donc vous présenter plus bas les principaux thèmes ayant été abordés.

## Le Search Engine Marketing (SEM)

<img src="/assets/images/merakist-seo.jpg" alt="SEO letters" class="align-center" />


Dans les grandes lignes, le SEO fait parti du *Search Engine Marketing* (SEM) qui vise à augmenter la visibilité d'un site sur les moteurs de recherche voire sur les réseaux sociaux.

On distingue ainsi: 

* Les techniques de référencement naturel qui vont permettre d'améliorer le positionnement d'un site dans un moteur de recherche gratuitement. 
* Le référencement payant.
* Le *Social Media Optimization* ou SMO qui comprend les activités permettant de développer la visibilité d'une entreprise au travers des médias sociaux. 


## Les piliers du SEO

Lorsqu'on travaille le référencement naturel, deux éléments principaux sont à optimiser:

* Le contenu ou la sémantique: il faut veiller à choisir les bons mots et utiliser les mots-clés les plus pertinents. 
* Il faut attacher une importance à la syntaxe et veiller à bien structurer son contenu. Cela passe notamment par une bonne indentation, l'utilisation des balises en HTML (`<h1>`, `<section>` etc.), des meta-data et la propreté du code. 

## La performance

Il ne faut pas non plus négliger la performance du site. D'ailleurs, parmi les principaux KPI on va analyser le temps de requêtage entre le serveur et le navigateur, le temps de chargement du code html et le temps qui s'écoule jusqu'au début de l'affichage. 

> En moyenne sur une version desktop, il faut compter entre 2 et 2.5 sec entre l'envoi de la requête et l'affichage total de la page.

Voici deux leviers d'amélioration de la performance:

* Optimisation du JavaScript : Placer les scripts à la fin (`<body>`) pour que l'execution du script ne bloque pas le chargement des autres éléments.
* Optimisation des images: privilégier les formats png ou jpg et s'intéresser au lazy loading (i.e. tout ce qui va être en dessous de la zone de flottaison ne sera pas chargé).

## Problématiques liées à JavaScript: 

Il est actuellement difficile de traiter JavaScript pour 3 raisons principales:

* Les robots d'exploration des moteurs de recherche ne sont pas en mesure de comprendre JavaScript de manière efficiente.
* L'execution du script est gourmand en ressources serveur. 
* Absence de contenu HTML.

Afin de contourner ces problèmes, deux solutions peuvent être adoptées:

* Server Side Rendering (SSR) ou rendu côté serveur qui consiste à créer des pages HTML côté serveur et à les envoyer toutes faites aux navigateurs.
* Dynamic rendering ou affichage dynamique qui consiste à afficher un contenu spécifique en fonction du type de client (bot ou utilisateur).



<img src="/assets/images/element5-teaching.jpg" alt="red apple fruit on four pyle books" class="align-center" />

> **Leçons à retenir pour ma reconversion**
>
> En tant que développeuse, je prends conscience de l'influence directe de mon travail sur le référencement. Je dispose de plusieurs leviers d'optimisation comme la mise en place de fichiers HTML bien structurés, le choix du langage de programmation et également plusieurs autres éléments abordés lors du talk mais non mentionnés dans cet article (par exemple le maillage pour accroitre la popularité d'une page grace aux urls ou encore la mise en place d'un sitemap pour indiquer au bot les pages à explorer en priorité).
>
> Maxime nous a également partagé une boite à outils SEO dont voici les principaux éléments:
>
> - Web developer tools ;
> - Wappalyzer pour connaitre le CMS ou framework d'un site ;
> - Le plugin View Rendered Source pour observer les différences entre le contenu HTML et le contenu JS ;
> - L'outil Sitemap Generator pour facilement générer des sitemap ;
> - Le Page Rank Simulator pour mesurer l'importance des pages d'un siteweb.



Si vous avez des commentaires ou ressources à partager, n'hésitez pas à me contacter. 

Je vous remercie,

Claire

<div>
<p style="font-size:10px">Photo credits:</p>
<a style="background-color:white;color:black;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:10px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@webaroo?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Webaroo"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Webaroo</span></a>

<a style="background-color:white;color:black;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:10px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@merakist?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Merakist"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Merakist</span></a>

<a style="background-color:white;color:black;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:10px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@element5digital?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Element5 Digital"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Element5 Digital</span></a>

</div>