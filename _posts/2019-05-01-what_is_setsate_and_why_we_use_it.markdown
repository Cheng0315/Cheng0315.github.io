---
layout: post
title:      "What is setState() and why we use it"
date:       2019-05-01 16:18:07 -0400
permalink:  what_is_setsate_and_why_we_use_it
---


setState() is a method provided to us by React. What this method does is it update the state of a component and let react knows that a state has been updated and that the component that contains the state should re-render itself. If we try to modify the state directly, e.g.

```
class PlateForm extends Component {

  constructor(props) {
    super(props);

    this.handleInputChange = this.handleInputChange.bind(this);
		
    this.state = {
      name: '',
      description: ''
    };
  }
	
  handleInputChange(e) {
    this.state.name = e.target.value;
  }
}
```
, nothing would happen as React would not know about the change and would not re-render the component.
