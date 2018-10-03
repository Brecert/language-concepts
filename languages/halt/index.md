```
body
  .navbar
    props: prop {
      name: height
      default: 10px
    }
    draw: from vec(0%, 0%) to vec(height, 100%)

  main
    // Fills everything in container
    draw: from vec(0, 0) to vec(100%, 100%)
    
  ```
