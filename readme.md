![Deloitte Digital](https://raw.githubusercontent.com/DeloitteDigital/DDBreakpoints/master/docs/deloittedigital-logo-white.png)

# React Habitat Redux ![Build Status](https://travis-ci.org/DeloitteDigitalAPAC/react-habitat-redux.svg?branch=develop)

This library brings [Redux](http://redux.js.org/) capabilities to [React-Habitat](https://github.com/DeloitteDigitalAPAC/react-habitat)

## Installing

Install with Node Package Manager (NPM)

`npm install react-habitat react-habitat-redux --save-dev`

*Note* npm deprecated auto installing of peer dependencies since npm@3, so you will additionally need to install these dependencies if you haven't already.

- Redux `npm install redux --save-dev`
- React-Redux `npm install react-redux --save-dev`
- React `npm install react --save-dev`
- React-Dom `npm install react-dom --save-dev`

## Usage

[React Habitat Documentation](https://github.com/DeloitteDigitalAPAC/react-habitat)

When configuring the React Habitat Bootstrapper, you'll want to use the Redux Container instead of the default one like so:


```javascript
import ReactHabitat                 from 'react-habitat';
import ReduxHabitat                 from 'react-habitat-redux';
import { createStore }              from 'redux';

import configureStore               from './store/configureStore'
import SomeReactComponent           from './SomeReactComponent';
import AnotherReactComponent        from './AnotherReactComponent';

class MyApp extends ReactHabitat.Bootstrapper {
    constructor(){
        super();
        
        // Create a store
        const store = configureStore();

        // Create a new 'Redux' container builder for the store
        var container = new ReduxHabitat.Container(store);

        // Register your top level component(s)
        container.register('SomeReactComponent', SomeReactComponent);
        container.register('AnotherReactComponent', AnotherReactComponent);

        // Finally, set the container
        this.setContainer(container);
    }
}

// Always export a 'new' instance so it immediately evokes
export default new MyApp();
```

It's important that you pass in the store object if you want redux 'connect' to work automatically.

## Want to contribute?

* Got an amazing idea to make this better?
* Found an annoying bug?

Please don't hesitate to raise an issue through GitHub or open a pull request to show off your fancy pants coding skills - we'll really appreciate it!

## Key Contributors

### Deloitte Digital Australia
* @jennasalau

## Who is Deloitte Digital?

**Part Business. Part Creative. Part Technology. One hundred per cent digital.**

Pioneered in Australia, Deloitte Digital is committed to helping clients unlock the business value of emerging technologies. We provide clients with a full suite of digital services, covering digital strategy, user experience, content, creative, engineering and implementation across mobile, web and social media channels.

[http://www.deloittedigital.com/au](http://www.deloittedigital.com/au)

## LICENSE (BSD-3-Clause)
Copyright (C) 2015, Deloitte Digital. All rights reserved.

React Habitat Redux can be downloaded from: https://github.com/DeloitteDigitalAPAC/react-habitat-redux

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
this list of conditions and the following disclaimer in the documentation
and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its contributors
may be used to endorse or promote products derived from this software without
specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
