```
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>58.0</apiVersion>
    <isExposed>true</isExposed>
    <masterLabel>gC_Exp_Theme_Layout</masterLabel>
    <description>Gares et Connexions Experience Site</description>
    <targets>
        <target>lightningCommunity__Theme_Layout</target>  
    </targets>
</LightningComponentBundle>
```
---
```
<template>
    <div class="theme-container">
        <div class="theme-header">
            <slot data-f6-region name="header"></slot>
        </div>
        <div class="theme-content">
            <slot data-f6-region></slot>
        </div>
        <div class="theme-footer">    
            <slot data-f6-region name="footer"></slot>
        </div>
    </div>    
</template>
```
---
```
import { LightningElement } from 'lwc';

/**
 * @slot header
 * @slot footer
 */
export default class GC_Exp_Theme_Layout extends LightningElement {}
```
---
```
.theme-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    min-width: 100%;
    height: 100%;
    min-height: 100%;
    margin: 0px;
    padding: 0px;
    background-color: #fff;
}

.theme-header {
    width: 100%;
    min-width: 100%;
    margin: 0; 
    padding: 0;
}

.theme-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    max-width: 1000px;
    margin: 10px 0 0 0; 
    padding: 0;
}

.theme-footer {
    width: 100%;
    min-width: 100%;
    margin: 0; 
    padding: 0;
}
```
---
```
<script>
    var newStyleSheet = document.createElement("link");
    newStyleSheet.rel = "stylesheet";
    newStyleSheet.type = "text/css";
    newStyleSheet.href = "/resource/My_Ressources/css/main.css?" + Date.now();
    document.getElementsByTagName("head")[0].appendChild(newStyleSheet);
</script>
```
