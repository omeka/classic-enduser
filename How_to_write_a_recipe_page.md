How to write a recipe page
==========================


"Recipe" pages are intended to demonstrate real problem and solutions in
developing addons for Omeka. They should be relatively concise examples
of how to use the tools in Omeka to produce specific effects or perform
specific tasks. Often, they will demonstrate how different functions
work together, and in that way supplements the individual function documentation pages.

Often, a thread from the forums or the dev list will make excellent
candidates to transform into a recipe.

Depending on the nature and complexity of the recipe, they could follow
different structuring principles. But, the following rough structure will help guide your readers. The [Default Item Thumbnail Images](Recipes/Default_Item_Thumbnail_Images.html "Recipes/Default Item Thumbnail Images") recipe is a great example.

-   Problem - A brief description of the problem or question. If it is
    based on an existing thread in the forums or dev list, include a
    link to it in a See Also list
-   Solution(s) - Your discussion of the solution. These should show
    real code examples, and careful explanations of how they work.
    -   Functions used - If the solution makes use of Omeka functions,
        provide a list of links to the documentation for those pages.

Start your page by adding a link to it under either the "Plugins" or
"Themes" subsection of Recipes on the [main documentation](../codex.1.html#Recipes "Documentation") page with this template.

    [[Recipes/My_Recipe|My Recipe]]

This template can help you get started with the recipe itself.

    == Problem ==
    * See also
    == Solution 1 ==
    === Functions Used ===
    * [[Functions/foo|foo()]]
    * [[Functions/foo|foo()]]
    == Solution 2 ==
    === Functions Used ===
    * [[Functions/foo|foo()]]
    * [[Functions/foo|foo()]]


    [[Category:Recipes]]

When adding a snippet of your code, use this template to make it more
readable:

    <source lang="php">
    // your code here
    </source>
