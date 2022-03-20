library(magick)


sleepy_cat <- image_read("https://cdn.pixabay.com/photo/2017/09/09/09/11/cat-2731418_960_720.jpg") %>%
  image_scale(500)

confused_cat <- image_read("https://wpimg.pixelied.com/blog/wp-content/uploads/2021/02/27223954/Hell-Yeah-GIF.gif") %>%
  image_scale(500)

happy_cat <- image_read("https://wpimg.pixelied.com/blog/wp-content/uploads/2021/02/27223954/Hell-Yeah-GIF.gif") %>%
  image_scale(500)

stats_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#000000") %>%
  image_annotate(text = "Statistics",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

comp_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#000000") %>%
  image_annotate(text = "Computer\nScience",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

ds_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#000000") %>%
  image_annotate(text = "Data\nScience",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

first_row <- c(sleepy_cat, stats_text) %>%
  image_append()

second_row <- c(confused_cat, comp_text) %>%
  image_append()

third_row <- c(happy_cat, ds_text) %>%
  image_append()

c(first_row, second_row, third_row) %>%
  image_append(stack = TRUE)
