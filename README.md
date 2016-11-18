# Learn-React-1

    Basic introduction to coding in React-Native. Design an app that displays a list of Taylor Swift albums 
    and an associated link to the amazon page to buy the album. Made many reusable components for future projects 
    including cards and buttons. 

NOTES:



>> react-native init albums

    AppRegistry.registerComponent('albums', ( ) => App );


* 1 component per file
    
        const Header = ( ) => (
          <Text> Albums </Text>
        )

* export default componentName;

    styling lives inside components

to make something the max width:   

    imageStyle: {
        height: 300,
        flex: 1,
        width: null
      }    

 // to get console.log( )
    CMD D -  Debug Menu

// AJAX //

    npm install —save axios
    import axios from ‘axios’


  // Component Level State  //
  Initialize:
     
        class AlbumList extends Component {
          state = { };
        }

Use built in setState method:
// note. it takes an object as an argument
    
    .then(response => this.setState({ albums: response.data}));

props: parent to child communication

objects rendered from an array need to have a unique key
    
    <Text key={ album.title }>{ album.title }</Text>

Passing form parent to child:

    <Card>
      <Text>{props.album.title}</Text>
    </Card>

    <View style={styles.containerStyle}>
      {props.children}
    </View>
    
NOTE:     if a component is passed from one component to another,
                it is available in props.children

NOTE:         plan ahead needed for designing layouts

  // LAYOUTS //
// Its all about the flex-box

To make components next to each other, put them in separate views. Then: 
    
        flex-direction: ‘row'
This affects the direction justifyContent aligns components.

     //  IMAGES  //

    Images do not automatically fill up the space in which they are placed.
MUST specify the width and height.

<Image source={{uri: }}/>


    //  DESTRUCTURING  //  

    const AlbumDetail = ({album}) => {
       const { title, artist, thumbnail_image } = album;
    }

         const { thumbnailStyle, headerContentStyle } = styles;



// SCROLLING //

Identify component

    import ScrollView instead of View
    
ScrollView requires a style of flex: 1 of its parent component.

// BUTTONS //


    const Button = ({onPress}) => {
        return (
            <TouchableOpacity
            style={buttonStyle}
            onPress={onPress} >
              <Text style={textStyle}>Click Me!</Text>
            </TouchableOpacity>

      );
    };

//  LINKING  //

    import { Text, View, Image, Linking } from 'react-native';
    
    <Button
     onPress={() => Linking.openURL(url)}
    />








