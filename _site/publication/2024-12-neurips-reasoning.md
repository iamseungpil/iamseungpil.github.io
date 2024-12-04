

<!doctype html>
<html lang="en" class="no-js">
  <head>
    

<meta charset="utf-8">



<!-- begin SEO -->









<title>Reasoning Abilities of Large Language Models through the Lens of Abstraction and Reasoning (Extended Abstract of the below paper) - Seungpil Lee</title>







<meta property="og:locale" content="en-US">
<meta property="og:site_name" content="Seungpil Lee">
<meta property="og:title" content="Reasoning Abilities of Large Language Models through the Lens of Abstraction and Reasoning (Extended Abstract of the below paper)">


  <link rel="canonical" href="http://localhost:4001/publication/2024-12-neurips-reasoning.md">
  <meta property="og:url" content="http://localhost:4001/publication/2024-12-neurips-reasoning.md">



  <meta property="og:description" content="The existing methods for evaluating the inference abilities of Large Language Models (LLMs) have been results-centric, making it difficult to assess the inference process. We introduce a new approach using the Abstract and Reasoning Corpus (ARC) dataset to evaluate the inference and contextual understanding abilities of large language models in a process-centric manner. ARC demands rigorous logical structures for problem-solving, making it a benchmark that facilitates the comparison of model inference abilities with humans. Experimental results confirm that while large language models possess weak inference abilities, they still lag in terms of logical coherence, compositionality, and productivity. Our experiments highlight the reasoning capabilities of LLMs, proposing development paths for achieving human-level reasoning.">





  

  





  <meta property="og:type" content="article">
  <meta property="article:published_time" content="2025-01-01T00:00:00-08:00">








  <script type="application/ld+json">
    {
      "@context" : "http://schema.org",
      "@type" : "Person",
      "name" : "Seungpil",
      "url" : "http://localhost:4001",
      "sameAs" : null
    }
  </script>






<!-- end SEO -->


<link href="http://localhost:4001/feed.xml" type="application/atom+xml" rel="alternate" title="Seungpil Lee Feed">

<!-- http://t.co/dKP3o1e -->
<meta name="HandheldFriendly" content="True">
<meta name="MobileOptimized" content="320">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<script>
  document.documentElement.className = document.documentElement.className.replace(/\bno-js\b/g, '') + ' js ';
</script>

<!-- For all browsers -->
<link rel="stylesheet" href="http://localhost:4001/assets/css/main.css">

<meta http-equiv="cleartype" content="on">
    

<!-- start custom head snippets -->

<link rel="apple-touch-icon" sizes="57x57" href="http://localhost:4001/images/apple-touch-icon-57x57.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="60x60" href="http://localhost:4001/images/apple-touch-icon-60x60.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="72x72" href="http://localhost:4001/images/apple-touch-icon-72x72.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="76x76" href="http://localhost:4001/images/apple-touch-icon-76x76.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="114x114" href="http://localhost:4001/images/apple-touch-icon-114x114.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="120x120" href="http://localhost:4001/images/apple-touch-icon-120x120.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="144x144" href="http://localhost:4001/images/apple-touch-icon-144x144.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="152x152" href="http://localhost:4001/images/apple-touch-icon-152x152.png?v=M44lzPylqQ">
<link rel="apple-touch-icon" sizes="180x180" href="http://localhost:4001/images/apple-touch-icon-180x180.png?v=M44lzPylqQ">
<link rel="icon" type="image/png" href="http://localhost:4001/images/favicon-32x32.png?v=M44lzPylqQ" sizes="32x32">
<link rel="icon" type="image/png" href="http://localhost:4001/images/android-chrome-192x192.png?v=M44lzPylqQ" sizes="192x192">
<link rel="icon" type="image/png" href="http://localhost:4001/images/favicon-96x96.png?v=M44lzPylqQ" sizes="96x96">
<link rel="icon" type="image/png" href="http://localhost:4001/images/favicon-16x16.png?v=M44lzPylqQ" sizes="16x16">
<link rel="manifest" href="http://localhost:4001/images/manifest.json?v=M44lzPylqQ">
<link rel="mask-icon" href="http://localhost:4001/images/safari-pinned-tab.svg?v=M44lzPylqQ" color="#000000">
<link rel="shortcut icon" href="/images/favicon.ico?v=M44lzPylqQ">
<meta name="msapplication-TileColor" content="#000000">
<meta name="msapplication-TileImage" content="http://localhost:4001/images/mstile-144x144.png?v=M44lzPylqQ">
<meta name="msapplication-config" content="http://localhost:4001/images/browserconfig.xml?v=M44lzPylqQ">
<meta name="theme-color" content="#ffffff">
<link rel="stylesheet" href="http://localhost:4001/assets/css/academicons.css"/>

<script type="text/x-mathjax-config"> MathJax.Hub.Config({ TeX: { equationNumbers: { autoNumber: "all" } } }); </script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/latest.js?config=TeX-MML-AM_CHTML' async></script>

<!-- end custom head snippets -->

  </head>

  <body>

    <!--[if lt IE 9]>
<div class="notice--danger align-center" style="margin: 0;">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</div>
<![endif]-->
    

<div class="masthead">
  <div class="masthead__inner-wrap">
    <div class="masthead__menu">
      <nav id="site-nav" class="greedy-nav">
        <button><div class="navicon"></div></button>
        <ul class="visible-links">
          <li class="masthead__menu-item masthead__menu-item--lg"><a href="http://localhost:4001/">Seungpil Lee</a></li>
          
            
            <li class="masthead__menu-item"><a href="http://localhost:4001/cv/">CV</a></li>
          
        </ul>
        <ul class="hidden-links hidden"></ul>
      </nav>
    </div>
  </div>
</div>

    





<div id="main" role="main">
  


  <div class="sidebar sticky">
  



<div itemscope itemtype="http://schema.org/Person">

  <div class="author__avatar">
    
    	<img src="http://localhost:4001/images/seungpil_profile.jpg" class="author__avatar" alt="Seungpil Lee">
    
  </div>

  <div class="author__content">
    <h3 class="author__name">Seungpil Lee</h3>
    <p class="author__bio">Undergraduate in Gwangju Institute of Science and Technology</p>
  </div>

  <div class="author__urls-wrapper">
    <button class="btn btn--inverse">Follow</button>
    <ul class="author__urls social-icons">
      
        <li><i class="fa fa-fw fa-map-marker" aria-hidden="true"></i> Gawngju, South Korea</li>
      
      
      
      
        <li><a href="mailto:iamseungpil@gm.gist.ac.kr"><i class="fas fa-fw fa-envelope" aria-hidden="true"></i> Email</a></li>
      
      
       
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
        <li><a href="https://scholar.google.com/citations?user=iPfrGWAAAAAJ&hl=ko"><i class="fas fa-fw fa-graduation-cap"></i> Google Scholar</a></li>
      
      
      
      
      
    </ul>
  </div>
</div>

  
  </div>


  <article class="page" itemscope itemtype="http://schema.org/CreativeWork">
    <meta itemprop="headline" content="Reasoning Abilities of Large Language Models through the Lens of Abstraction and Reasoning (Extended Abstract of the below paper)">
    <meta itemprop="description" content="The existing methods for evaluating the inference abilities of Large Language Models (LLMs) have been results-centric, making it difficult to assess the inference process. We introduce a new approach using the Abstract and Reasoning Corpus (ARC) dataset to evaluate the inference and contextual understanding abilities of large language models in a process-centric manner. ARC demands rigorous logical structures for problem-solving, making it a benchmark that facilitates the comparison of model inference abilities with humans. Experimental results confirm that while large language models possess weak inference abilities, they still lag in terms of logical coherence, compositionality, and productivity. Our experiments highlight the reasoning capabilities of LLMs, proposing development paths for achieving human-level reasoning.">
    <meta itemprop="datePublished" content="January 01, 2025">
    

    <div class="page__inner-wrap">
      
        <header>
          <h1 class="page__title" itemprop="headline">Reasoning Abilities of Large Language Models through the Lens of Abstraction and Reasoning (Extended Abstract of the below paper)
</h1>
          
        
        
        
          <p>Published in <i>In NeurIPS Workshop on System-2 Reasoning at Scale, 2024</i>, 2025 </p>
        
        
             
        
    
        </header>
      

      <section class="page__content" itemprop="text">
        <p>The existing methods for evaluating the inference abilities of Large Language Models (LLMs) have been results-centric, making it difficult to assess the inference process. We introduce a new approach using the Abstract and Reasoning Corpus (ARC) dataset to evaluate the inference and contextual understanding abilities of large language models in a process-centric manner. ARC demands rigorous logical structures for problem-solving, making it a benchmark that facilitates the comparison of model inference abilities with humans. Experimental results confirm that while large language models possess weak inference abilities, they still lag in terms of logical coherence, compositionality, and productivity. Our experiments highlight the reasoning capabilities of LLMs, proposing development paths for achieving human-level reasoning.</p>

<p><a href="https://arxiv.org/abs/2403.11793">Download paper here</a></p>

<!-- Recommended citation: Your Name, You. (2010). "Paper Title Number 2." <i>Journal 1</i>. 1(2). -->

        
      </section>

      <footer class="page__meta">
        
        




      </footer>

      

<section class="page__share">
  
    <h4 class="page__share-title">Share on</h4>
  

  <a href="https://twitter.com/intent/tweet?text=http://localhost:4001/publication/2024-12-neurips-reasoning.md" class="btn btn--twitter" title="Share on Twitter"><i class="fab fa-twitter" aria-hidden="true"></i><span> Twitter</span></a>

  <a href="https://www.facebook.com/sharer/sharer.php?u=http://localhost:4001/publication/2024-12-neurips-reasoning.md" class="btn btn--facebook" title="Share on Facebook"><i class="fab fa-facebook" aria-hidden="true"></i><span> Facebook</span></a>

  <a href="https://www.linkedin.com/shareArticle?mini=true&url=http://localhost:4001/publication/2024-12-neurips-reasoning.md" class="btn btn--linkedin" title="Share on LinkedIn"><i class="fab fa-linkedin" aria-hidden="true"></i><span> LinkedIn</span></a>
</section>

      


  <nav class="pagination">
    
      <a href="http://localhost:4001/publication/2024-03-18-TIST" class="pagination--pager" title="Reasoning Abilities of Large Language Models: In-Depth Analysis on the Abstraction and Reasoning Corpus
">Previous</a>
    
    
      <a href="#" class="pagination--pager disabled">Next</a>
    
  </nav>

    </div>

    
  </article>

  
  
</div>


    <div class="page__footer">
      <footer>
        <!-- start custom footer snippets -->
<a href="/sitemap/">Sitemap</a>
<!-- end custom footer snippets -->

        

<div class="page__footer-follow">
  <ul class="social-icons">
    
      <li><strong>Follow:</strong></li>
    
    
    
    
    
    <li><a href="http://localhost:4001/feed.xml"><i class="fa fa-fw fa-rss-square" aria-hidden="true"></i> Feed</a></li>
  </ul>
</div>

<div class="page__footer-copyright">&copy; 2024 Seungpil. Powered by <a href="http://jekyllrb.com" rel="nofollow">Jekyll</a> &amp; <a href="https://github.com/academicpages/academicpages.github.io">AcademicPages</a>, a fork of <a href="https://mademistakes.com/work/minimal-mistakes-jekyll-theme/" rel="nofollow">Minimal Mistakes</a>.</div>

      </footer>
    </div>

    <script src="http://localhost:4001/assets/js/main.min.js"></script>




  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', '', 'auto');
  ga('send', 'pageview');
</script>






  </body>
</html>
