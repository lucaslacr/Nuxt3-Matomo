# Nuxt3-Matomo
Tutorial and code to add Matomo to a nuxt 3 project (very easy)

## 1 add Vue Matomo
in your terminal enter the following command
```
npm install --save vue-matomo
```

## 2 add Nuxt plugin
Add file your-project/**plugins/super-matomo-plugin.js** to the project with this :
```
import { defineNuxtPlugin } from '#app'
import VueMatomo from 'vue-matomo'

export default defineNuxtPlugin((nuxtApp) => {
  nuxtApp.vueApp.use(VueMatomo, {
    host: 'https://your-matomo-domain-address.com',
    siteId: 1, 
    // Enables automatically registering pageviews on the router
    router: nuxtApp.$router,
    enableLinkTracking: true,
    requireConsent: false,
    trackInitialView: true,
    disableCookies: true,
    requireCookieConsent: false,
  })
})
```
**If you are using Server Side Rendering** (SSR) you have to add '.client' in your file name.

exemple : your-project/plugins/super-matomo-plugin.client.js

## 3 change the Matomo server address 

change the line **host: 'https://your-matomo-domain-address.com',**


## 4 register your plugin 
Nuxt 3 auto-import your plugin, so it's done

That it, your are a boss

