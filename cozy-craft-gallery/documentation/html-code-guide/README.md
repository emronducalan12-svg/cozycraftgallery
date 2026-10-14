# HTML Code Guide

This folder explains the HTML used by Cozy Craft Gallery in beginner-friendly language. The complete, working HTML is still in the project-root file `cozy-craft-gallery.html`; this guide describes where its code is and what it does rather than making a second copy that could get out of date.

## How to open the HTML

In VS Code, open the `cozy-craft-gallery` folder, then open `cozy-craft-gallery.html`. The browser reads this file and turns its tags into the visible web page. The CSS files in `css/` control how those tags look and respond to selections.

## Page map

Use the section IDs shown below to find each area quickly. In VS Code, press **Ctrl+F** and search for an ID, such as `id="about"`. Line numbers can change as the page is edited.

| Search for | What that area contains |
|---|---|
| `<head>` | Page title, mobile settings, browser icons, web fonts, and links to all CSS files. |
| `class="state-input"` | Hidden radio inputs used to hold product quantities and selected custom gifts. |
| `class="site-header"` | Brand logo and navigation links. |
| `id="home"` | Welcome banner and introduction. |
| `id="collections"` | Links to the Crochet and Fuzzy Wire collections. |
| `id="best-sellers"` | Featured product cards. |
| `id="custom-gifts"` | Custom gift idea cards and their selection labels. |
| `id="about"` | About Us copy and the image frame. The picture is hidden by CSS, not removed from the HTML. |
| `id="social"` | Social-media links and inline SVG icons. |
| `id="crochet"` / `id="fuzzy-wire"` | Main product listings for each collection. |
| `id="detail-crochet-bag"` (or another `id="detail-..."`) | A product's detail view. Search for `detail-` to find the others. |
| `id="bag"` | Shopping bag rows, quantity display, and estimated total. |
| `id="order"` | Selected-product panels and the customer order form. |
| `id="terms"` | Terms and conditions. |
| `id="contact"` | Contact information. |
| `<footer class="site-footer">` | Footer branding and helpful links. |
| `id="login"` | Login screen demonstration. It does not check or store a real account. |

## HTML tags used in this page

An HTML tag is written inside angle brackets. Most have an opening tag and a closing tag, for example `<p>Text</p>`. Some, such as `<img>` and `<input>`, do not wrap text and have no closing tag.

### Page structure and text

| Tag | Simple explanation | Used for |
|---|---|---|
| `<!DOCTYPE html>` | Declares a modern HTML document. | First line of the page. |
| `<html>` | Wraps the whole document. | The page root; `lang="en"` identifies its language. |
| `<head>` | Holds page setup, not the main visible content. | Title, metadata, icons, fonts, and CSS links. |
| `<meta>` | Gives browser or search information. | Text encoding, mobile viewport, and page description. |
| `<title>` | Sets the browser-tab title. | “Cozy Craft Gallery”. |
| `<link>` | Connects an external file or resource. | Loads CSS, icons, and fonts. |
| `<body>` | Contains the page content. | Everything displayed or used by the website. |
| `<header>` | Groups introductory or top-area content. | Site header and section headers. |
| `<nav>` | Groups navigation links. | Main menu and footer menus. |
| `<main>` | Marks the main content of the page. | Holds the shop sections and product views. |
| `<section>` | Groups one topic or page area. | Home, collections, About Us, bag, order form, and terms. |
| `<article>` | Groups one standalone item. | Product and custom-gift cards. |
| `<footer>` | Marks end-of-page information. | Site footer. |
| `<h1>`-`<h4>` | Headings of different levels. | Main page title, section titles, and product names. |
| `<p>` | A paragraph. | Descriptions, introductions, notes, and policies. |
| `<strong>` | Marks important text, usually shown bold. | Tips, labels, and important order notes. |
| `<em>` | Emphasizes text, usually shown italic. | Short emphasized phrases. |
| `<div>` | A general-purpose block container. | Groups card content, form layouts, and other elements. |
| `<span>` | A general-purpose inline container. | Styles part of a line, button label, badge, or icon. |
| `<i>` | An inline element used here as a CSS counter helper. | Hidden tally markers that help calculate the bag display. |

### Links, images, lists, and icons

| Tag | Simple explanation | Used for |
|---|---|---|
| `<a>` | A clickable link. | Navigation, product details, and buttons that jump to page sections. |
| `<img>` | Displays an image file. | Product photos, logos, and illustrations. |
| `<ul>` | Starts an unordered (bulleted) list. | Navigation menus and footer links. |
| `<li>` | One item in a list. | Each menu or footer link. |
| `<svg>` | Holds a scalable vector drawing. | Social-media icons embedded directly in the HTML. |
| `<path>` | Draws a line or shape inside an SVG. | Shapes that make up some social icons. |
| `<circle>` | Draws a circle inside an SVG. | A circular part of an icon. |
| `<rect>` | Draws a rectangle inside an SVG. | A rectangular part of an icon. |

### Forms and choices

| Tag | Simple explanation | Used for |
|---|---|---|
| `<form>` | Groups fields that collect or submit information. | Login demonstration and order form. |
| `<fieldset>` | Groups related form fields. | Customer information and item/order information. |
| `<legend>` | Names a fieldset. | Headings such as “About you” and “Your items”. |
| `<label>` | Names a field or makes a control clickable. | Form labels and the styled Add to Bag / gift-choice controls. |
| `<input>` | Creates a single form control. | Hidden radio choices and customer name, phone, email, and password fields. |
| `<select>` | Creates a drop-down menu. | Product selection and delivery/meetup preference in the order form. |
| `<optgroup>` | Groups related choices inside a drop-down. | Separates Crochet and Fuzzy Wire products in the product menu. |
| `<option>` | One choice inside a drop-down. | Individual choices in the order form. |
| `<textarea>` | Creates a multi-line text box. | Customer customization notes. |
| `<button>` | Creates a button control. | Form-related actions. |

### Definition lists

| Tag | Simple explanation | Used for |
|---|---|---|
| `<dl>` | Starts a list of terms and their descriptions. | Contact details and customization-fee information. |
| `<dt>` | The term or label in a definition list. | Labels such as “Location”. |
| `<dd>` | The value or description for a term. | The address or details associated with its label. |

## HTML patterns used by the website

### 1. A link to another section

```html
<a href="#about">About Us</a>
```

`href="#about"` looks for the element with `id="about"` and moves the page to it. This is how the navigation works without separate page files.

### 2. A product card

```html
<article class="product-card">
  <div class="product-media">
    <img src="assets/products/crochet/bag-crochet.jpg" alt="Crochet bag">
  </div>
  <div class="product-info">
    <h3 class="product-name">Bag Crochet</h3>
    <p class="product-desc">A handmade crochet bag.</p>
  </div>
</article>
```

`article` groups one product. The `class` values connect the elements to styles in `css/03-components.css`. `src` gives the image path, and `alt` describes the image for accessibility.

### 3. Product quantity selection

The page has hidden radio inputs near the beginning of the body. Each product has one radio for each quantity (zero through five). A visible label elsewhere points to a radio by matching its `for` value to that radio's `id`.

```html
<input type="radio" id="q-crochet-bag-1" name="Bag item: Bag Crochet"
       value="Qty 1" form="order-form">
<label for="q-crochet-bag-1">Add to Bag</label>
```

Clicking the label selects that radio. The CSS file `css/08-bag-state.css` checks which radio is selected and shows the matching bag row, button state, quantity, and total. The `form="order-form"` attribute associates the radio with the order form even though the radio is located outside the form element.

### 4. Custom gift selection

Each gift card has a label connected to a hidden gift radio input. CSS shows which gift has been chosen and includes it in the order display.

```html
<input type="radio" id="g-sweetheart" name="Custom gift idea"
       value="Sweetheart Bundle" form="order-form">
<label for="g-sweetheart">Choose This Gift</label>
```

### 5. Order form fields

```html
<label for="o-name">Customer name</label>
<input type="text" id="o-name" name="Name" required>
```

The label's `for` matches the input's `id`, so clicking the label focuses the field. `name` identifies the submitted value, and `required` asks the browser to prevent an empty submission.

### 6. Image paths

```html
<img src="assets/products/crochet/bag-crochet.jpg"
     alt="Bag Crochet" width="600" height="600">
```

`src` is a relative path from the HTML file to the image. `alt` is the accessible text description. `width` and `height` tell the browser the image's expected dimensions.

## Common HTML attributes

- **`class`**: style hooks shared by elements, such as `product-card` or `btn`.
- **`id`**: a unique name, often used as a link destination or CSS state selector.
- **`href`**: a link destination. `#bag` points to the element with `id="bag"`.
- **`src`**: the file path for an image.
- **`alt`**: an image description. Use `alt=""` only for decorative images.
- **`type`**: tells an input what kind of control it is, such as `radio`, `text`, or `email`.
- **`name`**: groups radio choices and names form values.
- **`value`**: the value represented by a form choice.
- **`for`**: connects a label to the input whose `id` matches it.
- **`required`**, **`minlength`**, **`maxlength`**, and **`pattern`**: built-in browser checks for form values.
- **`aria-label`**, **`aria-labelledby`**, and **`aria-hidden`**: accessibility information for assistive technologies.
- **`loading="lazy"`**: asks the browser to wait to load an off-screen image until it is needed.

## How the code works together

1. The browser opens `cozy-craft-gallery.html` and builds the page from its HTML tags.
2. The `<link rel="stylesheet" ...>` elements in `<head>` load the files in `css/`.
3. CSS class and ID selectors style the HTML and control which views are visible.
4. Clicking a link changes the URL fragment, for example to `#about` or `#bag`; CSS uses that fragment to show the corresponding view.
5. Selecting a radio input changes its `:checked` state. CSS uses that state to update the bag and gift selection display.

This project has no JavaScript. Its interactive-looking controls are implemented with HTML form controls and CSS. The login is only a demo, and the order form uses a placeholder `mailto:` email address until the shop's real address is entered.

## If you are replacing the hidden gift or About Us pictures

The HTML image elements are still there. Change the `src` value to the path of the replacement image:

```html
<img src="assets/gifts/my-new-gift.jpg" alt="Description of the new gift">
```

Then remove or change the matching `visibility: hidden` CSS rule. Custom-gift images are hidden in `css/03-components.css`; the About Us image is hidden in `css/02-layout.css`. The image frame/space is maintained by the surrounding HTML and CSS.
