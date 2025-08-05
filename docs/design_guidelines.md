# **Detailed Design Guidelines & Technical Specs for Lovable LLM Experimentation Platform**

---

## **1\. Color Palette & Usage**

| Color Name | Hex Code | Usage | Notes |
| ----- | ----- | ----- | ----- |
| Primary Blue Gradient | \#1E3A8A | Main brand color, buttons, links, accents | Use gradient from \#1E3A8A to \#3B5AC4 for backgrounds or highlights |
| Secondary White | \#FFFFFF | Backgrounds, text on primary blue | Ensure contrast ratio \> 4.5:1 for accessibility |
| Dark Gray Text | \#333333 | Primary body text | For readability on white background |
| Light Gray Background | \#F5F7FA | Page backgrounds, cards | Soft contrast for separation |
| Accent Blue Light | \#3B5AC4 | Hover states, secondary buttons | Use for interactive elements |
| Error Red | \#E53E3E | Error messages, alerts | Use sparingly, ensure contrast |
| Success Green | \#38A169 | Success messages, confirmations | Use sparingly |

Accessibility: All text colors on backgrounds must meet WCAG AA contrast standards. Use tools like axe or Lighthouse to verify.

---

## **2\. Typography**

| Element | Font Family | Size (px) | Line Height | Weight | Usage |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Headings H1 | Inter, sans-serif | 32 | 40 | 700 (Bold) | Page titles, main headers |
| Headings H2 | Inter, sans-serif | 24 | 32 | 600 (Semi-bold) | Section headers |
| Headings H3 | Inter, sans-serif | 18 | 28 | 600 (Semi-bold) | Subsection headers |
| Body Text | Inter, sans-serif | 16 | 24 | 400 (Regular) | Paragraphs, descriptions |
| Small Text / Tooltips | Inter, sans-serif | 12 | 16 | 400 (Regular) | Help text, labels |
| Buttons | Inter, sans-serif | 16 | 24 | 600 (Semi-bold) | Button labels |

Font Weights: Use CSS variables for font weights for consistency:

css

\--font-weight-bold: 700;  
\--font-weight-semibold: 600;  
\--font-weight-regular: 400;

\--font-weight-medium: 500;

---

## **3\. Spacing & Layout**

### **Grid System**

* Use a 12-column grid with 16px gutters.  
* Max container width: 1200px centered.  
* Responsive breakpoints:  
  * Mobile: \< 600px (single column)  
  * Tablet: 600px \- 900px (6-8 columns)  
  * Desktop: \> 900px (12 columns)

### **Spacing Scale (all in px)**

| Size Name | Value | Usage Examples |
| ----- | ----- | ----- |
| XS | 4 | Small gaps between icons/text |
| S | 8 | Padding inside buttons, inputs |
| M | 16 | Margin between form fields, cards |
| L | 24 | Section padding, larger gaps |
| XL | 32 | Page padding, main container gaps |

### **Padding & Margin Guidelines**

* Page container: padding-left/right: 24px (L), padding-top/bottom: 32px (XL)  
* Cards: padding: 16px (M), margin-bottom: 24px (L)  
* Buttons: padding: 12px 24px (S horizontal, S vertical)  
* Form inputs: padding: 12px (S), margin-bottom: 16px (M)  
* Headers: margin-bottom: 16px (M)  
* Between sections: margin-top: 32px (XL)

---

## **4\. UI Components**

### **Buttons**

* Primary button: background gradient (\#1E3A8A to \#3B5AC4), white text, border-radius: 6px  
* Secondary button: white background, primary blue text, border: 1px solid \#1E3A8A  
* Disabled state: gray background (\#CCCCCC), gray text (\#666666), no pointer events  
* Hover state: lighten background by 10%, add subtle box-shadow

### **Inputs & Forms**

* Border: 1px solid \#CCCCCC, border-radius: 6px  
* Focus state: border-color \#3B5AC4, box-shadow: 0 0 0 3px rgba(59, 90, 196, 0.3)  
* Placeholder text: \#999999  
* Error state: border-color \#E53E3E, error message text below input in red

### **Cards**

* Background: \#FFFFFF  
* Border-radius: 8px  
* Box-shadow: 0 2px 8px rgba(0,0,0,0.1)  
* Padding: 16px (M)  
* Margin-bottom: 24px (L)

### **Modals**

* Background overlay: rgba(0,0,0,0.5)  
* Modal container: max-width 600px, padding 24px (L), border-radius 8px, white background  
* Close button top-right corner, accessible via keyboard

---

## **5\. Iconography & Imagery**

* Use SVG icons for scalability and crispness.  
* Icons primarily white or primary blue (\#1E3A8A) depending on background.  
* Use minimalistic style consistent with brand.  
* Provide alt text for all icons/images for accessibility.

---

## **6\. Interaction & States**

| Element | Default State | Hover State | Focus State | Disabled State |
| ----- | ----- | ----- | ----- | ----- |
| Button | Primary blue gradient | Slightly lighter gradient | Box-shadow \+ border highlight | Gray background/text |
| Input | Gray border | Border color \#3B5AC4 | Box-shadow \+ border color | Gray border, no input |
| Card | White background | Slight shadow increase | N/A | N/A |
| Link | Primary blue text | Underline \+ darker blue | Outline focus ring | Gray text, no pointer |

---

## **7\. Accessibility**

* Color contrast: All text and interactive elements meet WCAG AA.  
* Keyboard navigation: All interactive elements focusable and operable via keyboard.  
* Screen reader labels: Use aria-labels and roles appropriately.  
* Focus indicators: Visible outlines on focus for inputs, buttons, links.  
* Responsive design: Layout adapts gracefully on mobile/tablet/desktop.

---

## **8\. Example CSS Variables (for easy theming)**

css

:root {  
  \--color-primary-start: \#1E3A8A;  
  \--color-primary-end: \#3B5AC4;  
  \--color-white: \#FFFFFF;  
  \--color-text-dark: \#333333;  
  \--color-bg-light: \#F5F7FA;  
  \--color-error: \#E53E3E;  
  \--color-success: \#38A169;

  \--font-family-base: 'Inter', *sans-serif*;  
  \--font-weight-bold: 700;  
  \--font-weight-semibold: 600;  
  \--font-weight-regular: 400;

  \--spacing-xs: 4px;  
  \--spacing-s: 8px;  
  \--spacing-m: 16px;  
  \--spacing-l: 24px;  
  \--spacing-xl: 32px;

  \--border-radius: 6px;  
  \--box-shadow-light: 0 2px 8px rgba(0,0,0,0.1);  
}

---

## **9\. Wireframe Layout Suggestions**

* Dashboard: Left vertical nav (fixed width 240px), main content area with 12-column grid.  
* Experiment Setup Wizard: Centered card with stepper on top, form fields stacked with consistent spacing.  
* Analytics Dashboard: Top filter bar with multi-select dropdowns, main chart area with line/bar charts, drill-down panel on right or below.  
* Modals: Centered overlay with clear close button, consistent padding.  
* 

