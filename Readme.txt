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
				-						<FlatList>												-insted of ScrollView we can use
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
elevation ------------just in android work----------------> saye ijad mikone barae android...				-dakhele style estefade mishe...
shadowColor, shadowOffset, shadowOpacity, shadowRadius ---> barae IOS estefade mishe
LiniearGradient ------------------------------------------> barae expo hast va az expo import mishe 		-mesle hamun gradiant hae css kar mikone		#expo install expo-linear-gradient			<LinearGradient colors={['#1111','#2222']} style={styles.}
borderBottomWidth ----------------------------------------> koloftie border ro dar nazar migire
color ----------------------------------------------------> range font
maxLength ------------------------------------------------> dakhele input estefade mishe va hade axar tule input ro barresi mikone 
keyboardType='number-pad' --------------------------------> noe keyboard moshakhas mikone
autoCapitalize -------------------------------------------> dakhele TextInput estefade mishe
autoCorrect ----------------------------------------------> dakhele TextInput estefade mishe 
<ImageBackground resizeMode='cover' imageStyle={}> -------> az react-native import mishe
Alert.alert() --------------------------------------------> alert mide
<SafeAreaView> -------------------------------------------> ghesmate ghabele namayesh ro pooshesh mide
20
================================================================================================================================================
05-
================================================================================================================================================
Dimensions ---> Dimensions.get('window').width
			mitoonim bahash andaze safhe ro b dast biarim, 'window' dakhele android javab mide, barae IOS har do javab mide

<KeyboadAvoidingView style={} behavior='position'> ---> import from 'react-native' ---> ba in mitoonim keyboard va  modiriat konim

useWindowDimentions ---> import from 'react-native' ---> const {width, height} = useWindowDimentions()
platform ---> import from 'react-native' ---> platform.os ya platform.select ... ---> style ha modiriat mishe nahashun

================================================================================================================================================
06-
================================================================================================================================================
 react navigation:
	npm install @react-navigation/native
	expo install react-native-screens react-native-safe-area-context

	import { NavigationContainer } from '@react-navigation/native'

	const Stack = createNativeStackNavigator()
	
	<NavigationContainer>
		<Stack.Navigator>
			<Stack.screen name='' component={} />
		</Stack.Navigator>
	</NavigationContainer>

	navigation.navigate('esm', {  })

	Route prop reference:
		each screen component in your app is provide with the route prop automaticlly.
			{key, name of the screen, path, params, navigat










