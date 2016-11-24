# Sane ListView
Why do we need all this datasource nonsense?!

## Usage

Just like any other react-native ListView, except the datasource is passed as props (rowsById and rowsIdArray):

~~~
<SaneListView
  rowsById={{id1: rowA, id2: rowB}}
  rowsIdArray={['id1', 'id2']}
  renderRow={this.renderRow}
/>
~~~

**A simple example:**

~~~
import SaneListView from 'react-native-sane-listview';
~~~

and then in your class

~~~
constructor(props) {
	super(props);
	this.state = {
		data: [{name:'Dan'},{name:'Lisa'}]
	};	
	
	reload = () => {
		this.setState({'data':[{name:'John'}]});
	};
		
	setTimeout(reload, 3000);
}
render() {
	return (
		<SaneListView style={{top:20}}
			rowsById={this.state.data}
			renderRow={(rowData) => <Text>{rowData.name}</Text>}
		/>
	);
}
~~~
