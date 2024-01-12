Allows creating and reusing UI taxonomies inside and across projects. Object Repository can used to build UI APIs for your application

*Key Features*
1. Centralized  storage
2. reusability
3. version control
4. collaboration
5. metadata and documentation
6. search and discovery
7. dependencies management
8. security and access control

*Structure*

1. Application:
		1. Mobile
		2. Desktop/web
2. Version
	- Applications can have multiple versions
3. Screen
	- top-level window of an application can only be created under an app version
4. UI Element
	- An object on the screen with a descriptor and metadata. It can be of multiple types.


*Key features*
- UI Descriptors
	- A UI Descriptor is a superset of selectors. It holds information for uniquely identifying elements on the screen.
- ui applications
	- A UI Application is a targeted application that can have multiple versions and each version can have multiple screens. 
-  screens
	- Screens are UI Scopes that are either extracted from activities inside the workflow or are generated at element capture time. A screen groups together multiple elements belonging to the same screen. 
- ui elements
	- UI Elements contain full or partial element selectors, anchor selectors, screen and element image capture context, and other metadata that describes the element on the screen.
- ui libraries
	- A UI Library is an encapsulation of elements grouped by applications, application versions, and screens. 
- ui activities
	-  UI Activities allows you to view a list of all your UI activities inside your process.

UI Library structure
- application > version > screen > ui elements

Object Repository Creation Options -  An object repository is a collection of elements grouped by applications, versions, and screens.
	- Can come from Local Project or from a library

Object Repository Panel
- You can create a repository using Capture Elements button in the Object Repository. Can capture all the elements of an application using Computer Vision and add to the Object Repository.
- Can create a  new library that can be installed in other projects as a dependency. Also, you can update an existing library if you exit the recorder before capturing all the desired.
- Add descriptors to the Snippets panel to reuse them, or extract them as UI libraries.
- Access objects from UI libraries installed as dependencies to the current project.

Options in the Object Repository panel.
- Expand All	
- Collapse All	
- Refresh	
- Add a new Element under this screen 	
- Capture Elements

Manual Creation of a Repository
- Create a UI Application
	- create a UI application by clicking on the plus sign in the Descriptors tab or right-click Project Descriptors in the same tab and select Create Application.
- Create a screen
	- create a screen by selecting an app for example here Calculator app, click the plus sign or right-click your application and select Create Screen.
- Create a UI Element
	- create a UI Element by selecting the app screen, click the plus sign or right-click the screen and select Create Element.

*Creating and Publishing a UI Library*




## How to use Object Repository with Recorders

You can add or reuse descriptors by clicking on the icon inside the activity, or you can select *Options > Add to Object Repository* to add the element.


**How to add elements From Activities to a Repository**

You can add more UI elements directly from the Designer panel that supports selectors, like Click or Type Into.

You can drag and drop a screen or element on top of an activity in your workflow using Object Repository. The object's image, arguments, and other details are automatically added to the activity.


**Updating an UI Library**
Right click in the object repository and select the "Capture elements" to inclu

  
Right-click the UI Elements in the Object Repository, select Edit Descriptor and recapture or edit the Descriptors


### Editing a Descriptor

Two scenarios:
1. Online editing
	- In the Descriptors tab, right-click an element and select Edit Descriptor. The selection screen opens allowing you to capture a different element, edit selectors, and anchors.
2. Offline editing
	- The application or browser can not be accessed on the current machine; either due to the app not being installed, or the machine is offline. The element's selectors are made visible allowing changes to be made.

You can also edit a screen descriptor, in the descriptor tab.

You can edit the application path or browser URL, application arguments, window selector, and select whether only applications with a title that is an exact match can be used in the automation.



## 

Incorporate the following best practices while working with Object Repository:

- **Reusability :** You can achieve reusability through different means, such as local elements, snippets, and UI libraries in the Object Repository.
    
- **Use Descriptive Names**: Use meaningful and descriptive names for objects in the repository. Avoid generic names such as "Button1" and "Link2" as they can become confusing as time progresses.
    
- **Organize Objects:** Organize objects within a repository by grouping them together by screen, type of object (buttons, input fields, etc.), or any other logical categorization.
    
- **Scalability:** It is important to design your object repository so that it can grow with your application. As new features are added, ensure the repository can support these changes without becoming inefficient.
    
- **Version Control:** When publishing a new version of the same UI library, make sure to properly add the new version number to the Publish window.

