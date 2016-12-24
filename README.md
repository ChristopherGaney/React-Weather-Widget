# React-Weather-Widget

I wanted to embed a weather widget into my React site, but I couldn't find any react-specific npm modules that created a nice multi-day forecast. I had been thinking about using iframes to sandbox third-party code in React components, and then I stumbled upon this page: http://blog.darksky.net/forecast-embeds/ where they offer a simple iframe to embed a weather widget in your html.

 <iframe id="forecast_embed" type="text/html" frameborder="0" height="245" width="100%" src="http://forecast.io/embed/#lat=42.3583&lon=-71.0603&name=Downtown Boston"> </iframe> 

It worked great, right out of the box. The only difficulty I experienced was getting the iframe to re-render when the location changed. Adding a key to the iframe solved the problem. 

<iframe id="forecast_embed" key={this.state.lat} type="text/html" frameBorder="0" height="245" width="90%" src={"http://forecast.io/embed/#lat=" + this.state.lat + "&lon=" + this.state.lng + "&name=event"}> </iframe>
