---
layout: page
title: Search
permalink: /search/
---

<div id="search-container">
	<input type="text" id="search-input" placeholder="Enter a search term..." autofocus>
	<ul id="results-container"></ul>
</div>

<script src="{{ site.baseurl }}/assets/simple-jekyll-search.min.js" type="text/javascript"></script>

<script>
	SimpleJekyllSearch({
		searchInput: document.getElementById('search-input'),
		resultsContainer: document.getElementById('results-container'),
		searchResultTemplate: `
		<a href="{url}"><h1>{title}</h1></a>
		<div class="post-metadata"><p class="post-date">{date}</p></div>`,
		json: '/assets/search.json'
	});
</script>
