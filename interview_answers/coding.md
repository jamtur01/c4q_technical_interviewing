# Coding Exercise

There are many ways to solve the problem.  This is one solution.

```
function getProducts() {
  var products = [
    {
      id: "3",
      name: "Truman Set",
      description: "This set has all you need to get started with Harry's. A great shave at a fair price.",
      price: "15",
    },
    {
      id: "10",
      name: "The Winston",
      description: "Made of zinc with a polished chrome body and strategically placed grips, the Winston is designed for effortless glide and precise control.",
      price: "20",
    },
    {
      id: "33",
      name: "Harry's Travel Kit",
      description: "Specially-designed for optimal packing and to contain spills, this Italian cotton-nylon travel kit is perfect for every guy on the go.",
      price: "25",
    },
  ];

  return products;
}


// Your app goes here, sample starting point below

var List = React.createClass({
  propTypes: {
    onOpenItem: React.PropTypes.func.isRequired,
  },

  renderItems(items) {
    return items.map((item) => {
      return (
        <li key={item.id}>
          <a href="#" onClick={() => this.props.onOpenItem(item)}>
            {item.name} - ${item.price}
          </a>
        </li>
      );
    });
  },

  render() {
    const items = getProducts();

    return (
      <ul>
        {this.renderItems(items)}
      </ul>
    );
  }
});

var Detail = React.createClass({
  render() {
    const item = this.props.item;

    if (!item) {
      return <div />;
    }

    return (
      <div>
        <h3>{item.name}</h3>
        <p>{item.description}</p>
        <p>${item.price}</p>
      </div>
     );
  }
});

var App = React.createClass({
  getInitialState() {
    return {
      openItem: null,
    };
  },

  handleOpenItem(item) {
    this.setState({
      openItem: item,
    });
  },

  render: function() {
    return <div>
      <List onOpenItem={this.handleOpenItem} />
      <Detail item={this.state.openItem} />
    </div>;
  }
});

ReactDOM.render(
  <App />,
  document.getElementById('container')
);
```
