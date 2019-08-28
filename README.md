## markdown-it-anchor

[markdown-it](https://github.com/markdown-it/markdown-it) support anchors.

## Usage

``` js
const md = require('markdown-it')()
    .use(require('@zeromake/markdown-it-anchor'), opt);
const env = {
    tocs: []
};

md.render(`## 1.Test\n\n## 2. Faset\n\n## 2.1 gg`, env);
// <h2>
// <a class="anchor" href="#1-Test">¶</a>1.Test</h2>
// <h2>
// <a class="anchor" href="#2-Faset">¶</a>2. Faset</h2>
// <h2>
// <a class="anchor" href="#2-1-gg">¶</a>2.1 gg</h2>
console.log(env.tocs);
// [
//    { id: '1-Test', title: '1.Test', level: 2 },
//    { id: '2-Faset', title: '2. Faset', level: 2 },
//    { id: '2-1-gg', title: '2.1 gg', level: 2 }
// ]
```

