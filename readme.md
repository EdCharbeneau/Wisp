#Wisp
##An ultra light Sass grid

Wisp consists of two Sass mixins that can perform most grid duties.
Ultra lightweight at just 783 bytes.

***row*** `row($nested: [false, true])`
Defines an element as a grid row. Use true/false to toggle nested grid gutters.

***column*** `column($column-width: [100%])`
Defines an element as a grid column. The element will occupy the assigned percentage of the grid space including gutters.

##Settings
Just two settings and a few pre-defined grid sizes. Grid sizes are easy to add and remove, just define a value between 1-100%.
    
    $layout-width: 980px; // For auto margins
    $gutter: 24px; // white space between columns
     
    // Predefined column widths
    // These are suggestions, feel free to add your own
     
    //golden ratio
    $golden-small: 38.2%;
    $golden-large: 61.8%;
     
    //thirds
    $one-third: 33.33%;
    $two-thirds: 66.66%;
     
    //quaters
    $one-quarter: 25%;
    $one-half: 50%;
    $three-quarters: 75%;

##Example (responsive mobile first)

*Sass:*
    @import "wisp";
    
    $large-device-width: 768px;
    
    // All the things
    section {
            @include row;
    }
    
    / Default (yay, moble first demo)
    @media only screen {
        .fifty-fifty {
             @include column;
        }
    }
    
    @media only screen and (min-width: $large-device-width) {
        .fifty-fifty {
             @include column($one-half);
        }
    }
    
*HTML:*
    
    <section>
        <div class="fifty-fifty">
            Content Left
        </div>
            <div class="fifty-fifty">
            Content Right
        </div>
    </section>