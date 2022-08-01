<script>

  import {Route} from 'tinro'; 
  import Blog from './Blog.svelte'
  import Portfolio from './Portfolio.svelte'

</script>

<main>
  <header>
    <h1>Jimmy's Cave</h1>
    <br>
    My private blog
  </header>
  <nav>
    <a href="/">Home</a>
    <a href="/portfolio">Portfolio</a>
  </nav>

  <Route path="/"><Blog/></Route>
  <Route path="/portfolio"><Portfolio/></Route>
</main>