
### 1. **Video and Audio Content**

-   **Evolution of video and audio on the web since the early 2000s**: In the early 2000s, using video and audio on the web required third-party plugins like Flash, QuickTime, and RealPlayer. These plugins were proprietary, had compatibility issues across browsers, and posed security risks. Over time, the HTML5 `<video>` and `<audio>` elements were introduced, offering native support for embedding multimedia directly within webpages without the need for external plugins. This shift also allowed for more standardized formats like MP4 for video and MP3 for audio, and better integration with JavaScript, enhancing multimedia control and functionality.
    
-   **The use of the `src` and `controls` attributes in the `<video>` element**: The `src` attribute specifies the source URL of the video file to be played. It allows the browser to locate and fetch the media. The `controls` attribute, when added to the `<video>` element, provides a default set of controls (play, pause, volume, and sometimes fullscreen) for the user to interact with the video.
    
-   **Why is it important to have fallback content inside the `<video>` element?**: Fallback content inside the `<video>` element is important to ensure accessibility and provide a backup when the browser does not support the `<video>` element or cannot read the specified video format. It may include a message or a link to an alternative format or a download option for the user.
    
-   **Story with `<audio>` and `<video>` as characters**: `<audio>` and `<video>` were once the best of friends, both trying to share their stories with the world. `<audio>` would sing songs, delivering sound with rhythm, while `<video>` told rich tales with moving images. One day, they realized they were much stronger together—`<video>` gave `audio` a visual presence, and `audio` gave `video` the power of sound. Now, when they unite, they tell stories that captivate both sight and sound, each enhancing the other’s strength.
    

### 2. **A Complete Guide to Grid**

-   **Difference between Grid layout and Flexbox**: Grid layout allows for two-dimensional layout control (both rows and columns), making it suitable for complex web designs where content is arranged in both directions. Flexbox is designed for one-dimensional layouts (either in a row or column), making it better for simpler designs like aligning items in a single line.
    
-   **Grid container, grid item, and grid line**:
    
    -   **Grid container**: The element that defines the grid, usually using `display: grid;`.
    -   **Grid item**: The individual child elements inside the grid container that are placed on the grid.
    -   **Grid line**: The horizontal and vertical lines that form the grid structure. These lines are used to place and align grid items.

### 3. **Responsive Images**

-   **Importance of responsive images**: Making images responsive ensures that they adjust to the screen size and resolution, improving user experience on various devices. This is crucial for mobile-first design as images can be resized, saved bandwidth, and load times can be optimized, leading to better performance on smaller devices.
    
-   **Attributes `srcset` and `sizes` in `<img>`**:
    
    -   **`srcset`** specifies multiple image sources for different screen resolutions or sizes, allowing the browser to choose the most appropriate image based on the viewport's size and resolution.
    -   **`sizes`** defines the sizes of the images at various breakpoints. For example, if the image takes up 50% of the screen width on mobile, `sizes` will help the browser choose an image that is appropriate for that width.
    
    **Example**:
    
    `<img src="image-1000px.jpg" 
         srcset="image-500px.jpg 500w, image-1000px.jpg 1000w, image-1500px.jpg 1500w" 
         sizes="(max-width: 600px) 100vw, 50vw" alt="Responsive Image">` 
    
    In this example, the browser chooses the best image based on the width of the screen and loads an appropriate resolution.
    
-   **How `srcset` is more helpful than CSS or JavaScript**: Unlike CSS or JavaScript, which can be used to adjust the image size or provide alternative sources with media queries, `srcset` allows the browser to automatically select the best image based on device capabilities (resolution and screen size) without needing extra scripting or CSS rules. This makes it more efficient and improves performance.
    

### 4. **Bookmark and Review**

-   **Images in HTML**: This topic is a review from a previous class, and it likely focuses on embedding images using the `<img>` tag, with attributes such as `src`, `alt`, `width`, and `height`. Additionally, responsive design principles for images are probably discussed.

### 5. **Other Embedding Technologies**

Other embedding technologies could refer to using `<iframe>` for embedding other web pages or content like maps, videos, or even games, and the use of `<object>` or `<embed>` elements for embedding different kinds of media, like PDFs or Flash content (though Flash is now obsolete).

### 1. **What is Object-Oriented Programming (OOP)?**

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of objects. Objects are instances of classes, which can contain data (attributes) and methods (functions) that operate on the data. OOP emphasizes principles like **encapsulation** (bundling data and methods), **inheritance** (reusing code through hierarchical relationships), **polymorphism** (allowing objects to be treated as instances of their parent class), and **abstraction** (hiding complex details while exposing only the necessary parts). OOP helps in organizing code in a more modular and reusable way, promoting better maintainability and scalability.

### 2. **To use CSS Grid, the parent element (container) must have the `display` property set to what value?**

To use CSS Grid, the parent element must have the `display` property set to `grid`:


`.container {
  display: grid;
}` 

### 3. **The Array method of _______ adds one or more elements to the end of an array.**

The Array method of **`push()`** adds one or more elements to the end of an array:


`let arr = [1, 2, 3];
arr.push(4, 5);  // arr becomes [1, 2, 3, 4, 5]` 

### 4. **The Array method of _______ removes the last element from an array.**

The Array method of **`pop()`** removes the last element from an array:


`let arr = [1, 2, 3];
arr.pop();  // arr becomes [1, 2]` 

### 5. **The Array method of _______ removes the first element from an array.**

The Array method of **`shift()`** removes the first element from an array:

`let arr = [1, 2, 3];
arr.shift();  // arr becomes [2, 3]` 

### 6. **The Array method of _______ adds one or more elements to the beginning of an array.**

The Array method of **`unshift()`** adds one or more elements to the beginning of an array:

`let arr = [1, 2, 3];
arr.unshift(0);  // arr becomes [0, 1, 2, 3]` 

### 7. **The Array method of _______ changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.**

The Array method of **`splice()`** changes the contents of an array by removing, replacing, or adding elements:

`let arr = [1, 2, 3, 4];
arr.splice(1, 2, 5, 6);  // arr becomes [1, 5, 6, 4]` 

In this example, `splice(1, 2, 5, 6)` starts at index 1, removes 2 elements, and adds `5` and `6` in their place.