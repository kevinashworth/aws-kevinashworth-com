---
layout: single
title: How to show a Material-UI V4/V5 Tooltip at the cursor
date: 2022-05-24 15:17:59
og_image: /assets/images/2022-05-24-tooltip-screenshot.png
categories:
- Blog
tags:
- Development
- JavaScript
- Material-UI
- Popper.js
- Programming
- React
---
Recently, I needed to place a tooltip at the tip of the cursor, and it took a little bit of trial and error to get it to work. Here is the code I used.

![screenshot of tooltip following mouse](/assets/images/2022-05-24-tooltip-screenshot.png)

## Material-UI V4 Tooltip

[Material-UI V4](https://v4.mui.com) uses the older [V1 of the Popper.js library](https://popper.js.org/docs/v1/). To get it to work, I followed the mouse and put its `position` in state, and then used the position to adjust the Tooltip's Popper using the `computeStyle` function:

{% highlight javascript %}
const computeStyleFn = (data) => {
  return {
    ...data,
    styles: {
      ...data.styles,
      left: `${position.clientX + 7}px`,
      top: `${position.clientY + 2}px`,
    },
  };
};
{% endhighlight %}

See a rudimentary React 17 demo repo in action at [CodeSandbox.io](https://codesandbox.io/s/github/kevinashworth/mui-v4-tooltip-demo?file=/src/Demo.js), or find the code [on GitHub](https://github.com/kevinashworth/mui-v4-tooltip-demo).

## Material UI V5 Tooltip

With [Material UI V5](https://mui.com/), the Popper.js library has been updated to [V2](https://popper.js.org/docs/v2/). It has a `followCursor` option availabe, so all we need to do here is figure out the offset that we want.

{% highlight javascript %}
{% raw %}
<Tooltip
  followCursor={true}
  PopperProps={{
    modifiers: [
      {
        name: "offset",
        options: {
          offset: [88, 2],
        },
      },
    ],
  }}
>
{% endraw %}
{% endhighlight %}

See a React 18 demo repo in action at [CodeSandbox.io](https://codesandbox.io/s/github/kevinashworth/mui-v5-tooltip-demo?file=/src/Demo.js), or check out the code [on GitHub](https://github.com/kevinashworth/mui-v5-tooltip-demo).
