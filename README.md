# Android-RoadMap-3 `v1.0.0-alpha01`

**Androidv14 - Level34**

## APP ARCHITECTURE - ADVANCE

### 1. Guide to app architecture

#### 1.1 About app architecture

- Mobile app user experiences
- Common architectural principles
    - Separation of concerns
    - Drive UI from data models
    - Single source of truth
    - Unidirectional Data Flow
- Recommended app architecture
    - Modern App Architecture
    - UI layer
    - Data layer
    - Domain layer
- Manage dependencies between components
- General best practices
- Benefits of Architecture

#### 1.2 UI layer

##### 1.2.1 About UI layer

- A basic case study
- UI layer architecture
- Define UI state
    - Immutability
    - Naming conventions in this guide
- Manage state with Unidirectional Data Flow
    - State holders
    - Types of logic
    - Why use UDF?
- Expose UI state
    - Additional considerations
- Consume UI state
    - Show in-progress operations
    - Show errors on the screen
- Threading and concurrency
- Navigation
- Paging
- Animations

##### 1.2.2 UI events

- UI event decision tree
- Handle user events
    - User events in RecyclerViews
    - Naming conventions for user event functions
- Handle ViewModel events
    - Consuming events can trigger state updates
- Navigation events
    - Navigation events when the destination is kept in the back stack
- Other use cases

##### 1.2.3 State holders and UI State

- Elements of the UI state production pipeline
    - UI state
    - Logic
- Android lifecycle and the types of UI state and logic
    - The UI state production pipeline
- State holders and their responsibilities
    - Types of state holders
- Business logic and its state holder
    - The ViewModel as a business logic state holder
- UI logic and its state holder
- Choose between a ViewModel and plain class for a state holder
- State holders are compoundable

##### 1.2.4 UI State production

- The UI state production pipeline
- State production APIs
- State production pipeline assembly
- Inputs in state production pipelines
    - One-shot APIs as sources of state change
    - Stream APIs as sources of state change
    - One-shot and stream APIs as sources of state change
- Output types in state production pipelines
- State production pipeline initialization

#### 1.3 Domain layer

- Naming conventions in this guide
- Dependencies
- Call use cases in Kotlin
- Lifecycle
- Threading
- Common tasks
    - Reusable simple business logic
    - Combine repositories
- Other consumers
- Data layer access restriction
- Testing

#### 1.4 Data layer

##### 1.4.1 About Data layer

- Data layer architecture
- Expose APIs
- Naming conventions in this guide
- Multiple levels of repositories
- Source of truth
- Threading
- Lifecycle
- Represent business models
- Types of data operations
    - UI-oriented operations
    - App-oriented operations
    - Business-oriented operations
- Expose errors
- Common tasks
    - Make a network request
    - Implement in-memory data caching
    - Save and retrieve data from disk
    - Schedule tasks using WorkManager
- Testing
    - Unit tests
    - Integration tests

##### 1.4.2 Build an offline-first app

- Design an offline-first app
- Model data in an offline-first app
    - The local data source
    - The network data source
    - Exposing resources
- Reads
    - Error handling strategies
- Writes
    - Write strategies
- Synchronization and conflict resolution
    - Pull-based synchronization
    - Push-based synchronization
    - Hybrid synchronization
- Conflict resolution
    - Last write wins
- WorkManager in offline-first apps

#### 1.5 Recommendations for Android architecture

- Layered architecture
- UI layer
- ViewModel
- Lifecycle
- Handle dependencies
- Testing
- Models
- Naming conventions

---

### 2. Modularization

#### 2.1 Guide to Android app modularization

- The growing codebase problem
- What is modularization?
- Benefits of modularization
- Common pitfalls
- Is modularization the right technique for me?

#### 2.2 Common modularization patterns

- High cohesion and low coupling principle
- Types of modules
    - Data modules
    - Feature modules
    - App modules
    - Common modules
    - Test modules
- Module to module communication
- Dependency inversion
    - Example
    - Dependency injection
    - Benefits
    - When to separate
    - How to implement?
- General best practices
    - Keep your configuration consistent
    - Expose as little as possible
    - Prefer Kotlin & Java modules

#### 2.3 Recipes

##### 2.3.1 Navigation best practices for multi-module projects

- The role of the `app` module
- Top-level navigation in app module
- Navigating across feature modules

---

### 3. Architecture components

#### 3.1 UI layer libraries

##### 3.1.1 Data Binding library

###### **3.1.1.1 About Data Binding**

- Using the Data Binding Library

###### **3.1.1.2 Get started**

- Build environment
- Android Studio support for data binding

###### **3.1.1.3 Layouts and binding expressions**

- Data objects
- Binding data
- Expression language
    - Common features
    - Missing operations
    - Null coalescing operator
    - Property references
    - Avoid null pointer exceptions
    - View references
    - Collections
    - String literals
    - Resources
- Event handling
    - Method references
    - Listener bindings
- Imports, variables, and includes
    - Imports
    - Variables
    - Includes

###### **3.1.1.4 Work with observable data objects**

- Observable fields
- Observable collections
- Observable objects
- Lifecycle-aware objects
    - Use StateFlow

###### **3.1.1.5 Generated binding classes**

- Create a binding object
- Views with IDs
- Variables
- ViewStubs
- Immediate binding
- Dynamic variables
- Background thread
- Custom binding class names

###### **3.1.1.6 Binding adapters**

- Set attribute values
    - Automatic method selection
    - Specify a custom method name
    - Provide custom logic
- Object conversions
    - Automatic object conversion
    - Custom conversions

###### **3.1.1.7 Bind layout views to Architecture Components**

- Use LiveData to notify the UI about data changes
- Use ViewModel to manage UI-related data
- Use an Observable ViewModel for more control over binding adapters

###### **3.1.1.8 Two-way data binding**

- Two-way data binding using custom attributes
- Converters
- Infinite loops using two-way data binding
- Two-way attributes

##### 3.1.2 View binding library

###### **3.1.2.1 About View binding**

- Setup
- Usage
    - Use view binding in activities
    - Use view binding in fragments
    - Provide hints for different configurations
- Differences from findViewById
- Comparison with data binding

###### **3.1.2.2 Migrate from Kotlin synthetics to Jetpack view binding**

- Update the Gradle file
- Update activity and fragment classes

##### 3.1.3 Lifecycle-Aware Components

###### **3.1.3.1 Lifecycles**

###### **3.1.3.1.1 Handling Lifecycles with Lifecycle-Aware Components**

- Lifecycle
- LifecycleOwner
    - Implementing a custom LifecycleOwner
- Best practices for lifecycle-aware components
- Use cases for lifecycle-aware components
- Handling on stop events

###### **3.1.3.1.2 Integrate Lifecycle with Compose**

- Collect lifecycle state with flows
- Run code on lifecycle events
    - LifecycleStartEffect
    - LifecycleResumeEffect

###### **3.1.3.2 ViewModel**

###### **3.1.3.2.1 About ViewModel**

- ViewModel benefits
    - Persistence
    - Access to business logic
- Jetpack Compose
- Implement a ViewModel
    - Use coroutines with ViewModel
- The lifecycle of a ViewModel
    - Clearing ViewModel dependencies
- Best practices
- Further information

###### **3.1.3.2.2 Create ViewModels with dependencies**

- ViewModels with CreationExtras
- Factories for ViewModel version older than 2.5.0

###### **3.1.3.2.3 ViewModel Scoping APIs**

- ViewModels scoped to the closest ViewModelStoreOwner
- ViewModels scoped to any ViewModelStoreOwner
- ViewModels scoped to the Navigation graph

###### **3.1.3.2.4 Saved State module for ViewModel**

- Setup
- Working with SavedStateHandle
    - LiveData
    - StateFlow
    - Experimental Compose's State support
- Supported types
    - Directly supported types
    - Saving non-parcelable classes
- SavedStateHandle in tests

###### **3.1.3.2.5 ViewModel APIs cheat sheet**

###### **3.1.3.3 LiveData**

- The advantages of using LiveData
- Work with LiveData objects
    - Create LiveData objects
    - Observe LiveData objects
    - Update LiveData objects
    - Use LiveData with Room
    - Use coroutines with LiveData
- LiveData in an app's architecture
- Extend LiveData
- Transform LiveData
    - Create new transformations
- Merge multiple LiveData sources

###### **3.1.3.4 Save UI states**

- User expectations and system behavior
    - User-initiated UI state dismissal
    - System-initiated UI state dismissal
- Options for preserving UI state
- Use ViewModel to handle configuration changes
- Use Saved instance state as backup to handle system-initiated process death
    - Hook into saved state using SavedStateRegistry
- Use local persistence to handle process death for complex or large data
- Managing UI state: divide and conquer
- Restore complex states: reassembling the pieces

###### **3.1.3.5 Use Kotlin coroutines with lifecycle-aware components**

- Add KTX dependencies
- Lifecycle-aware coroutine scopes
    - ViewModelScope
    - LifecycleScope
- Restartable Lifecycle-aware coroutines
    - Lifecycle-aware flow collection
- Suspend Lifecycle-aware coroutines
- Use coroutines with LiveData

##### 3.1.4 Paging library

###### **3.1.4.1 About Paging library**

- Benefits of using the Paging library
- Setup
- Library architecture
    - Repository layer
    - ViewModel layer
    - UI layer

###### **3.1.4.2 Load and display paged data**

- Define a data source
    - Select key and value types
    - Define the PagingSource
    - Handle errors
- Set up a stream of PagingData
- Define a RecyclerView adapter
- Display the paged data in your UI

###### **3.1.4.3 Page from network and database**

- Coordinate data loads
    - Paging lifecycle
- Basic usage
    - Create Room entities
    - Implement a RemoteMediator
    - Define the initialize method
    - Create a Pager
- Handle race conditions
- Manage remote keys
    - Item keys
    - Page keys
- Refresh in place

###### **3.1.4.4 Transform data streams**

- Apply basic transformations
    - Convert data
    - Filter data
- Add list separators
    - Convert the UI model
    - Transform the data stream
    - Handle separators in the UI
- Avoid duplicate work

###### **3.1.4.5 Manage and present loading states**

- Loading states
- Access the loading state with a listener
- Present the loading state with an adapter
    - Display the loading state as a header or footer
- Access additional loading state information
- Chain operators on LoadState

###### **3.1.4.6 Test your Paging implementation**

- UI layer tests
    - Testing transformations
- Data layer tests
    - PagingSource tests
    - RemoteMediator tests
- End-to-end tests

###### **3.1.4.7 Migrate to Paging 3**

- Benefits of migrating to Paging 3
- Migrate your app to Paging 3
    - DataSource classes
    - PagedList
    - PagedListAdapter

###### **3.1.4.8 Paging 2 library**

###### **3.1.4.8.1 About Paging 2 library**

- Setup
- Library architecture
    - PagedList
    - Data
    - UI
- Support different data architectures
    - Network only
    - Database only
    - Network and database
- Handle network errors
- Update your existing app
    - Custom paging solutions
    - Data loaded using lists instead of pages
    - Associate a data cursor with a list view using CursorAdapter
    - Load content asynchronously using AsyncListUtil
- Database examples
    - Observing paged data using LiveData
    - Observing paged data using RxJava2

###### **3.1.4.8.2 Display paged lists**

- Connect your UI to your view model
- Implement the diffing callback
- Diffing using a different adapter type
- Provide placeholders in your UI

###### **3.1.4.8.3 Gather paged data**

- Construct an observable list
- Define your own paging configuration
- Choose the correct data source type
- Notify when data is invalid
- Build your own data sources
- Consider how content updates work
- Provide data mapping

#### 3.2 Data layer libraries

##### 3.2.1 DataStore

- Preferences DataStore and Proto DataStore
- Using DataStore correctly
- Setup
    - Preferences DataStore
    - Proto DataStore
- Store key-value pairs with Preferences DataStore
    - Create a Preferences DataStore
    - Read from a Preferences DataStore
    - Write to a Preferences DataStore
- Store typed objects with Proto DataStore
    - Define a schema
    - Create a Proto DataStore
    - Read from a Proto DataStore
    - Write to a Proto DataStore
- Use DataStore in synchronous code
- Use DataStore in multi-process code

##### 3.2.2 WorkManager

###### **3.2.2.1 About WorkManager**

- Types of persistent work
- Features
    - Work constraints
    - Robust scheduling
    - Expedited work
    - Flexible retry policy
    - Work chaining
    - Built-In threading interoperability
- Use WorkManager for reliable work
- Relationship to other APIs
- Replacing deprecated APIs

###### **3.2.2.2 Getting started**

###### **3.2.2.2.1 Getting started with WorkManager**

- Define the work
- Create a WorkRequest
- Submit the WorkRequest to the system

###### **3.2.2.2.2 Define work requests**

- Overview
- Schedule one-time work
- Schedule expedited work
    - Quotas
- Executing expedited work
    - Backwards compatibility and foreground services
    - Worker
    - CoroutineWorker
    - Sample app
    - Deferred expedited work
- Schedule periodic work
    - Flexible run intervals
    - Effect of Constraints on Periodic Work
- Work constraints
- Delayed Work
- Retry and backoff policy
- Tag work
- Assign input data

###### **3.2.2.3 How-To-Guides**

###### **3.2.2.3.1 Work states**

- One-time work states
- Periodic work states
- Blocked state

###### **3.2.2.3.2 Managing work**

- Unique Work
    - Conflict resolution policy
- Observing your work
    - Complex work queries
- Cancelling and stopping work
- Stop a running Worker
    - onStopped() callback

###### **3.2.2.3.3 Observe intermediate worker progress**

- Update Progress
- Observing Progress

###### **3.2.2.3.4 Chaining work**

- Input Mergers
    - OverwritingInputMerger
    - ArrayCreatingInputMerger
- Chaining and Work Statuses

###### **3.2.2.3.5 Testing Worker implementation**

- Testing Workers
- Testing ListenableWorker and its variants

###### **3.2.2.3.6 Integration tests with WorkManager**

- Setup
- Concepts
- Structuring Tests
    - Basic Tests
- Simulate constraints, delays, and periodic work
    - Test Initial Delays
    - Testing Constraints
    - Testing Periodic Work

###### **3.2.2.3.7 Debug WorkManager**

- Enable logging
- Use adb shell dumpsys jobscheduler
- Request diagnostic information from WorkManager 2.4.0+

###### **3.2.2.4 Advanced Concepts**

###### **3.2.2.4.1 Custom WorkManager Configuration and Initialization**

- On-Demand Initialization
    - Remove the default initializer
    - Implement Configuration.Provider
- Custom initialization before WorkManager 2.1.0
    - Default initialization
    - Custom initialization

###### **3.2.2.4.2 Asynchronous work with Java threads**

- Concurrency libraries
- Examples overview
- Create multiple threads
- Execute in a background thread
    - Make the request
    - Trigger the request
    - Handle dependency injection
    - Execute in a background thread
    - Considerations
- Communicate with the main thread
- Use handlers
- Configure a thread pool

###### **3.2.2.4.3 Threading in Worker**

###### **3.2.2.4.4 Threading in CoroutineWorker**

- Running a CoroutineWorker in a different process

###### **3.2.2.4.5 Threading in RxWorker**

###### **3.2.2.4.6 Threading in ListenableWorker**

- Running a ListenableWorker in a different process

###### **3.2.2.4.7 Support for long-running workers**

- Creating and managing long-running workers
    - Kotlin
    - Java
- Add a foreground service type to a long-running worker
    - Declare foreground service types in app manifest
    - Specify foreground service types at runtime

###### **3.2.2.5 Migrating from Firebase JobDispatcher to WorkManager**

- Gradle setup
- From JobService to workers
    - JobService maps to a ListenableWorker
    - SimpleJobService maps to a Worker
- JobBuilder maps to WorkRequest
    - Setting up inputs for the Worker
    - Setting up Constraints for the Worker
    - Creating the WorkRequest (OneTime or Periodic)
- Scheduling work
- Cancelling work
- Initializing WorkManager

###### **3.2.2.6 Migrating from GCMNetworkManager to WorkManager**

- Migrate to WorkManager
    - Include the WorkManager libraries
    - Modify your manifest
    - Define the Worker
    - Schedule the work request
- API mappings
    - Constraint mappings
    - Other mappings
