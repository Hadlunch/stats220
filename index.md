# Hello Woerld!
**Welcome to my music world**
# About me
I'm currently a Stat220 student for Semester one 2022. I love memes and music especially pop music and Hip-Hop.
# 
Here is a meme I made by R package [magic](https://cran.r-project.org/web/packages/magick/vignettes/intro.html)
_This meme is sourced from Drake - Hotline Bling_
![Drake](https://user-images.githubusercontent.com/101852426/159155594-2e001dd1-940a-4c89-b18d-de32b2c60129.png)






# Here is the code of my meme!
library(magick)
Drake_yes <- image_read("https://m.media-amazon.com/images/M/MV5BZmQ2MzVhMTYtOTk0ZC00NzIwLWJiYjQtMjc3ZmE5ZDFhNTc4XkEyXkFqcGdeQXVyNjM0NzMyNTQ@._V1_.jpg") %>%
  image_scale(800)
Drake_yes
Drake_no <- image_read("https://realworldmusictheory.com/content/images/2021/01/6e52acce958795508a7ecbf6a3656c0190-11-drake-hotline-bling.2x.rhorizontal.w700.jpg") %>%
  image_scale(800)
Drake_no
Covid_text <- image_blank(width = 500, 
                       height = 600, 
                       color = "#000000") %>%
  image_annotate(text = "Covid",
                 color = "#FF0000",
                 size = 100,
                 font = "Impact",
                 gravity = "center")

CovidGone_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#000000") %>%
  image_annotate(text = "Covid\nGone",
                 color = "#FF0000",
                 size = 100,
                 font = "Impact",
                 gravity = "center")

first_row <- c(Drake_no, Covid_text) %>%
  image_append()

second_row <- c(Drake_yes, CovidGone_text) %>%
  image_append()

Drake <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

image_write(Drake, path = "Drake.png", quality = 75)
