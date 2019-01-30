# Vue Super Call
> This is a simple library to call super in vuejs application

### How to use in your project?
* Install it by `npm install vue-super-call`
* Add your main.js/index.js (entry file of your project) like following,
```javascript
import VueSuperMethod from 'vue-super-call'

Vue.prototype.$super = VueSuperMethod
```

### How to call super from method?
* The basic syntax is `this.$super(Mixin).yourMethod()`
* Proper example is following...
```javascript
// This is mixin
export default {
    name: 'MyMixin',
    methods: {
        sayHello() {
            return "Hello"
        }
    }
}


// Your Component
export default {
    name: 'MyComponent',
    mixins: [MyMixin],
    methods: {
        sayHello() {
            let parentMethodData = this.$super(MyMixin).sayHello()
            console.log(parentMethodData)
            console.log('I\'m from component after super call')
        }
    }
}

// Console Output
$ Hello
$ I'm from component after super call
```

**That's it :)**