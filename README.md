# highcanfly-algolia-vue3
This is a test Vue3 site tested in CodeSandbox at https://codesandbox.io/s/github/eltorio/highcanfly-algolia-vue3  
It is developped for our main website https://www.highcanfly.club  
It contains a AlgoliaSearch.vue wich can be simply imported in a Vue3 / Tailwindcss 3 / Font Awesome 6 site
```vue
    <algolia-search
      applicationId="ABJE27440A"
      searchKey="75cf07531eff71f751166e64704bacd6"
      filter="type:post"
    />
```
```javascript
import AlgoliaSearch from "@/components/AlgoliaSearch";
```  
It needs some dependecies:  
```json
  "dependencies": {
    "vue": "^3.2.31",
    "vue-instantsearch": "4.3.3",
    "@fortawesome/fontawesome-free": "~6.0.0"
  },
  "devDependencies": {
    "postcss": "^8.4.6",
    "tailwindcss": "^3.0.23",
    "vue-template-compiler": "^2.6.14"
  },
```
my base template @CodeSandbox https://codesandbox.io/s/vue-3-2-31-tailwindcss-3-0-23-fontawesome-6template-i8o5t6  

# [Algolia Search](https://www.algolia.com/)
Algolia gives us a free plan for our open source project.  
![thanks](https://res.cloudinary.com/hilnmyskv/image/upload/v1580296397/Algolia_com_Website_assets/logo-algolia-nebula-blue-full.png)  
Thank you

# HighCanFly site web (activement basé sur Vue Notus) <a href="https://twitter.com/HighCanFlyClub" target="_blank">![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&logo=twitter)</a>

![version](https://img.shields.io/badge/version-1.0.0-blue.svg) ![license](https://img.shields.io/badge/license-GPLv3-red.svg) <a href="https://github.com/eltorio/vue-highcanfly/issues?q=is%3Aopen+is%3Aissue" target="_blank">![GitHub issues open](https://img.shields.io/github/issues/eltorio/vue-highcanfly.svg)</a> <a href="https://github.com/eltorio/vue-highcanfly/issues?q=is%3Aissue+is%3Aclosed" target="_blank">![GitHub issues closed](https://img.shields.io/github/issues-closed-raw/eltorio/vue-highcanfly.svg)</a>
 <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licence Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Ce(tte) œuvre est mise à disposition selon les termes de la <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Licence Creative Commons Attribution -  Partage dans les Mêmes Conditions 4.0 International</a>.

![Vue Notus](https://repository-images.githubusercontent.com/448899125/ce3dc56f-2f1e-49dc-83d3-c6297308bf46?raw=true)
