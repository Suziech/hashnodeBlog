---
title: "[TailwindCSS] space-x-2"
seoTitle: "TailwindCSS: Understanding space-x-2"
seoDescription: "Learn how Tailwind CSS's `space-x-2` utility adds 8px horizontal spacing between sibling elements using `margin-left` or `margin-right`"
datePublished: Mon Nov 18 2024 05:36:10 GMT+0000 (Coordinated Universal Time)
cuid: cm3mlep1e000g09kz24wv5wkl
slug: tailwindcss-space-x-2
tags: space, tailwind-css

---

`space-x-2` is a Tailwind CSS utility class *(predefined small-scale classes)* used to add horizontal spacing *(gap)* between sibling elements(elements that share the same parent element) inside a container.

1. **Definition**
    
    * `space-x-2` adds horizontal spacing bewteen direct child elements.
        
    * the `2` refers to a predefined spacing value in Tailwind’s spacing scale, which by default equals `0.5rem (8px)`.
        
2. **How it works**
    
    * This class only applies spacing between child elements.
        
    * <mark>It uses the </mark> `margin-left` <mark>or </mark> `margin-right` <mark>property under the hood to create gaps between the items.</mark>
        
3. Example Code
    
    ```xml
    <div class="flex space-x-2">
      <div class="bg-red-500 h-10 w-10"></div>
      <div class="bg-blue-500 h-10 w-10"></div>
      <div class="bg-green-500 h-10 w-10"></div>
    </div>
    ```
    

* The container uses a `flex` layout.
    
* The `space-x-2` class adds 8px of horizontal spacing between each child (`div`).
    

![result](https://cdn.hashnode.com/res/hashnode/image/upload/v1731907445658/bb9132b3-d80c-43a7-bd2b-4ed28830ddb9.png align="center")

4. Tailwind’s default spacing scale
    
    * The numbers in `space-x-N` correspond to Tailwind’s spacing scale. Here’s an overview
        
    
    | **Class** | **Spacing Value** |
    | --- | --- |
    | `space-x-0` | `0rem` (0px) |
    | `space-x-1` | `0.25rem` (4px) |
    | `space-x-2` | `0.5rem` (8px) |
    | `space-x-3` | `0.75rem` (12px) |
    | `space-x-4` | `1rem` (16px) |
    | … | … |
    
    > 💬 I think it is very similar to `gap` property. it is very useful for adding space between elemenets.
    
    \[Tailwind-website-space-x-N\]([https://tailwindcss.com/docs/space](https://tailwindcss.com/docs/space))