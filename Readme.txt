Udemy - React Native - The Practical Guide [2022] 2022-5 Eng Sub
Subtitle: English
Quality: 720p
=================
www.downloadly.ir

*******************************************************************************************
================================================================================================================================================
01 - Getting Started
================================================================================================================================================
npm install -g expo-cli
expo init MyApp
		(expo.dev)
		choose a template: --> blank, ...
app.js:
		defrence between ReactJS vs. React-Native:

				ReactJS					React-Native
			-----------------------------------------
				<div>					<view>		----------->	*onClick nadare v bejash ma az <Pressable onPress={}> estefade mikonim
				<input>					<TextInput>	===props===>	onChange	onChangeText
				<p>						<Text>
				<button>				<Button 
											title='...'
											color='...'
											onPress={...}
										/>			===props===>		onClick		onPress		-style dehi b surat props hae az pish tarif shodas... mesle color={}
				-						<ScrollView>
				-						<FlatList numColumns={2}>								-insted of ScrollView we can use
				-						<Switch>
				-						<Pressable onPress={}>
				<img>					<Image source={require('../assets/images/goal.png')} />
				-						<SafeAreaView>											-ertefa fullscreen ro eslah mikone v tanzim mikone(IOS)
				

				*There is no CSS in React native but base on css syntax we can styling
				*react-native -> components -> basic components
				*for example: border: '1px solid red' not working and you should write ---> borderWidth: 2, borderColor: 'red', padding: 16

		StyleSheet.create({}) ---> StyleSheet imported from react-native

Expo Go app:
		you can see your app in real Android or IOS device

Android Studio or xcode (for ios):
		-android studio -> more actions -> virtual device manager -> create device -> after install choose play action

================================================================================================================================================
02 - React Native Basics [COURSE GOALS APP]
================================================================================================================================================
Styling:
	StyleSheet.create({}) 	--> Exp: <Text style={{margin:...}} />
	paddingY --> paddingHorizontal

Handling Events:
	function goalInputHandler(enteredText){
		console.log(enteredText)
	}

	function addGoalHandler(){}


	<TextInput onChangeText={goalInputHandler} placeholder='abcd' />
	<Button title='Add Goal' onPress={}/>
	
Hooks:
	useState from 'react'

Difrencess between two platform:
			------------------------------------------------------------------------------
				Android				vs				IOS
			------------------------------------------------------------------------------
	borderRadiuce:	in Text component border radiuse does not work in IOS and its better to assign in <View>
	color:		its better to put in <Text> component
	<Scrollview>:	alwaysBounceVertical prop is true in IOS by default --------> you can false it in both devices
	android_ripple:	android_ripple={{color:'#fff'}}		style={({pressed}) => pressed && styles.pressedItem}
			*android_ripple does not work in IOS and we must use style

		
		#behtare adat konam: borderRadiuce ro barae text dakhel view bezarim --- color ro dakhele Text bezaram --- android_ripple ro be surate style stefade konam


ScrollView:
	*view dosen't scrolling automaticly and it's better to use ScrollView in to the View

FlatList:
	*Optimizing lists
	*insted of ScrollView we can use <FlatList alwaysBounceVertical={false}>biiiib</FlatList>
	*instead of using .map, we must use this prpos:
		-data
		-renderitem
		-KeyExtractor --> it's work like key

	<view style={...}>
		<FlatList
			data={data}

			KeyExtractor={(item, index) => {
				return item.id or uniq key
			}}

			renderItem={itemData => {
				return (
					<View style=...>
						<Text>{itemData.item}</text>
					</view>
				)
			}}
	</view>

Modal:
	<Modal
		visible={}
		animationType=''
	></Modal>
	
================================================================================================================================================
04-Diving Deeper int components, layouts.. Game App
================================================================================================================================================
elevation ------------just in android work----------------> saye ijad mikone barae android...							-dakhele style estefade mishe...
shadowColor, shadowOffset, shadowOpacity, shadowRadius ---> barae IOS estefade mishe
LiniearGradient ------------------------------------------> barae expo hast va az expo import mishe 					-mesle hamun gradiant hae css kar mikone		#expo install expo-linear-gradient			<LinearGradient colors={['#1111','#2222']} style={styles.}
borderBottomWidth ----------------------------------------> koloftie border ro dar nazar migire
color ----------------------------------------------------> range font
maxLength ------------------------------------------------> dakhele input estefade mishe va hade axar tule input ro barresi mikone 
keyboardType='number-pad' --------------------------------> noe keyboard moshakhas mikone
autoCapitalize -------------------------------------------> dakhele TextInput estefade mishe
autoCorrect ----------------------------------------------> dakhele TextInput estefade mishe 
<ImageBackground resizeMode='cover' imageStyle={}> -------> az react-native import mishe
Alert.alert() --------------------------------------------> alert mide
<SafeAreaView> -------------------------------------------> ghesmate ghabele namayesh ro pooshesh mide
expo-vector-icons ----------------------------------------> <Ionicons name='md-remove' size={24} color='white' />		-bayad nasb koni
expo install expo-font -----------------------------------> barae avaz kardane font nasb mishe -------------------------> useFonts({
																															'open-sans': require(./assets/fonts/file.ttf)
																															})
expo install expo-app-loading------------splash-----------> import AppLoading from 'expo-app-loading'
<image source={require('location')} /> -------------------> import from 'react-native' ----------------------------------> mishe az uri bejae require estefade kard
================================================================================================================================================
05 - Building Adaptive User Interfaces (Adapt to Platform & Device Sizes)
================================================================================================================================================
Dimensions -----------------------------------------------> Dimensions.get('window').width ------------------------------> mitoonim bahash andaze safhe ro b dast biarim, 'window' dakhele android javab mide, barae IOS har do javab mide		

<KeyboadAvoidingView style={} behavior='position'> ---> import from 'react-native' ---> ba in mitoonim keyboard va  modiriat konim

useWindowDimentions ---> import from 'react-native' ---> const {width, height} = useWindowDimentions()
platform ---> import from 'react-native' ---> platform.os ya platform.select ... ---> style ha modiriat mishe nahashun

KeyboadAvoidingView -----> bayad dakhele root gharar begire va dakhele ScrollView ghara migire ----> bishtar barae IOS karbordie
platform ----> borderWidth: Platform.OS === 'android' ? 2 : 0 ************ borderWidth: Platform.select({ios: 0, android: 2})
StatusBar -----------------------------------------------> import {StatusBar} from 'expo-status-bar' ----------> un status darbare batrio anten ro mitoonim check konim k dark bashe ya light -----> root gharar migire
================================================================================================================================================
06- React Native Navigation with React Navigation [MEALS APP] ----------> documantion is in React Navigation
================================================================================================================================================
 react navigation: ---------------------------------------> {1-npm install @react-navigation/native, 
 															 2-expo install react-native-screens react-native-safe-area-context
															 3-npm install @react-navigation/native-stack}
	
	React Navigation Exp:

	import { NavigationContainer } from '@react-navigation/native'
	import { createNativeStackNavigator } from '@react-navigation/native-stack'

	const Stack = createNativeStackNavigator()
	
	<NavigationContainer>
		<Stack.Navigator screenOptions={{*STYLE BARAE HAME SAFEHA EMAL MISHE*}}>
			<Stack.screen name='' component={*NOT AS A JSX ELEMENT*} options={{title: 'All Categories'}} />
		</Stack.Navigator>
	</NavigationContainer>

-dakhele func ma in ro gharar midim k ba estefade az onPress handle mikonim:

	const function X(){
		navigation.navigate('screen name', { parametr ha ro inja midim barae estefade hae props tor })
	}

	*Tip: inja navigate jozi az navigation.params hastesh... props hae dg darim... mesle {goBack, ...}
	*Tip 2: props hae *navigation, route, ...* az tarighe <Stack.screen /> gerefte mishe

-mitoonim az useNavigation hook niz estefade kard
	import { useNavigation } from '@react-navigation/native'
	const navigation = useNavigation()
	

	Route prop reference:
		each screen component in your app is provide with the route prop automaticlly.
			{key, name of the screen, path, params, navigat


-import {useLayoutEffect} from 'react'
	mesle useEffect kar mikone ba in tafavote ke b mahze render shodane layout in hook render mishe

-adding button to header:
	<Stack.Screen name='mealDetail" component={component} options={{
		headerRight: () => {
			return <Text>In the header</Text>
		}
	}}

-import { crateDrawerNavigator } from '@react-navigation/drawer' ---------------------> menu az kenar miad va mitoonim estefade konim
	npm install @react-navigation/drawer

	dakhele NavigationContainer bayad gharar bedim...

	const Drawer = crateDrawerNavigator()

	<NavigationContainer>
		<Drawer.Navigator initialRouteName='user'>
			<Drawer.Screen name='name' component={component} />
		</Drawer.Navigator>
	</NavigationContainer>

	*initialRouteName: mige k aval koodoom safe bydefault biad bala,,,agar nazarimesh mire az avalin Drawer.Screen shooroo b khundan mikone...
================================================================================================================================================
07 - App-wide State Management with Redux & Context API
================================================================================================================================================