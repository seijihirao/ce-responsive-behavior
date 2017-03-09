# CustomElements..AppResponsiveBehavior

[![Bower version](https://badge.fury.io/bo/ce-responsive-behavior.svg)](https://badge.fury.io/bo/ce-responsive-behavior)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/seijihirao/ce-responsive-behavior)

Custom Element behavior to make your app responsive using polymer.

## INSTALL

```
$ bower install --save ce-responsive-behavior
```

## IMPORT

```HTML
    <link rel="import" href="../bower_components/ce-responsive-behavior/ce-responsive-behavior.html">
```

## USING

You can use the variables `isSmallScreen` and `isLargeScreen`
```HTML
<dom-module id="x-app">
    <template>
        <template is="dom-if" if="[[isSmallScreen]]">
            <div>This is a mobile app</div>
        </template>
        <template is="dom-if" if="[[isLargeScreen]]">
            <div>This is a desktop app</div>
        </template>
    </template>
    <script>
        Polymer({
            is: "x-app",
            behaviors: [
                CustomElements.AppResponsiveBehavior
            ],
        });
	</script>
</dom-module>
```

And create an *if* statement with `responsiveCase('caseSmall', 'caseLarge')`
```HTML
<dom-module id="x-app">
    <template>
        <style>
            div {
                background-color: #607D8B;
            }
            div.smallScreen {
                width: 100vw;
                height: 20vh;
            }
            div.largeScreen {
                width: 10vw;
                height: 10vh;
            }
        </style>
        <div class$="[[responsiveCase('smallScreen', 'largeScreen')]]">My App</div>
    </template>
    <script>
        Polymer({
            is: "x-app",
            behaviors: [
                CustomElements.AppResponsiveBehavior
            ],
        });
	</script>
</dom-module>
```