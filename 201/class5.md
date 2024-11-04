## Using Images in HTML

1.**Real-world use case for the `alt` attribute on a website**  
    The `alt` attribute provides alternative text for images, which is essential for screen readers used by visually impaired individuals. For example, on an e-commerce site, if a product image fails to load, the `alt` text (like "red cotton T-shirt") provides a description, allowing the user to understand what the image would have shown.

2. **Improving accessibility of images in HTML**  
    You can improve accessibility by:
    
    - Adding descriptive `alt` text for all images.
    - Including captions for complex images (like graphs) to describe their purpose or content.
    - Using `aria-labels` or `longdesc` attributes for more detailed descriptions when necessary.
3. **Use case for the `figure` element**  
    The `<figure>` element is useful when an image or visual content (like a chart) is part of the main content and needs a caption. For instance, in an educational article with a labeled diagram, `<figure>` can group the image and its caption together:
    
    `<figure>
        <img src="anatomy-diagram.png" alt="Anatomy Diagram">
        <figcaption>Diagram of the human anatomy</figcaption>
    </figure>`

4.  **Difference between GIF and SVG images**
    
    -   **GIF**: A file format that supports simple animations and has limited colors (256). It’s commonly used for small animations, like a blinking cursor.
    -   **SVG**: A scalable vector format ideal for logos and icons. Unlike GIFs, SVGs don’t lose quality when resized because they’re made from mathematical paths rather than pixels.
5.  **Image type for displaying a screenshot**  
    PNG is best for screenshots because it supports high quality and retains the details and sharpness of text, which is essential for readability in screenshots.
    

----------

## Using Color in CSS

1.  **Difference between foreground and background colors**
    
    -   **Foreground color**: This is the color of the text or any content displayed on an element.
    -   **Background color**: This is the color that fills the space behind the content. Think of a greeting card where the background might be red, and the text (foreground) might be white.
2.  **Adding character to a blog with color**  
    Using color can make the site more visually appealing:
    
    -   **Background color**: Choose a soft, neutral background to avoid overwhelming the reader.
    -   **Text color**: Use a dark or contrasting color for readability.
    -   **Accent colors**: Use for headings or links to draw attention.
3.  **Considerations for choosing fonts**  
    When selecting fonts:
    
    -   **Readability**: Ensure the font is clear and easy to read.
    -   **Consistency**: Use a limited number of fonts for a cohesive look.
    -   **Accessibility**: Choose fonts that are legible at various sizes.
4.  **Functions of `font-size`, `font-weight`, and `font-style`**
    
    -   **Font-size**: Adjusts the size of the text.
    -   **Font-weight**: Sets the boldness (e.g., light, normal, bold).
    -   **Font-style**: Alters the style (e.g., normal, italic).
5.  **Adding spacing around characters in an `h1` element**
    
    -   **Letter-spacing**: Adds space between each character.
    -   **Padding**: Adds space around the entire element, creating separation from surrounding content.