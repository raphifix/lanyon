---
published: false
layout: post
tags: R
---
Here's a helper function to import a directory of files into R. If you want to import files matching a certain pattern, you can enter the pattern as an argument.

```r
dir_to_df <- function(dir_path, pattern = NULL, verbose = TRUE){
  # ensure the path ends with a backslash
  dir_path <- ifelse(substr(dir_path, nchar(dir_path), nchar(dir_path)) == '/', dir_path, paste0(dir_path, '/'))
  # make sure pattern is a string
  if(!is.null(pattern) & class(pattern) != 'character'){
    stop('pattern must be a string')
  }
  
  # create placeholder list
  file_list <- list()
  # create vector of filenames and apply pattern if necessary
  if(is.null(pattern)){
    file_names <- list.files(dir_path)
  }else{
    file_names <- list.files(dir_path)[which(grepl(pattern, list.files(dir_path)))] 
  }
  # print info
  if(isTRUE(verbose)){
    print('The following files will be combined:')
    print(file_names)
  }
  # bring in files
  for(i in 1:length(file_names)){
    df <- read.csv(paste0(dir_path, file_names[i]), stringsAsFactors = F)
    file_list[[i]] <- df
  }
  # stack them
  full_df <- try(do.call('rbind', file_list))
  if(class(full_df) == 'try-error'){
    stop("Files couldn't be combined. Please ensure they are structurally equivalent.")
  }
  return(full_df)
}
```
