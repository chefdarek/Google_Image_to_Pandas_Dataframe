# Google_Image_to_Pandas_Dataframe


![alt text](http://66.media.tumblr.com/tumblr_ma3tldCx8B1r8vxluo1_500.gif "Space the Rainbow")

python 3.7 class GoogleImage_to_Labeled_Df(object):
      
    def __init__(self, list_of_labels, limit, path_string, size_string="medium", response = google_images_download.googleimagesdownload()):
        
        self.search_queries = list_of_labels
        
        self.size_string = size_string
        
        self.limit = limit
        
        self.path_string = path_string
        
        self.response = response
    

## Takes:

list_of_labels (search terms) 

limit (number of pictures you want)

path_string (where you would like the seperated folders of files labeled by search term, I knowww)

size_string="medium" (image size with option of large, medium or icon)

## Returns:

A pandas dataframe (limit*search_queries,2) shape of Numpy Array images

## Methods:

.get_images() it does not make you dinner or drive autonomously

.rename_loop() renames/enumerates all the files you merc'd from google image to the label name

.make_df() creates the df and prints the shape

.show_image(x) pass in a row and the image will return unlike your sanity

### To do

add scaling options

add tensorflow pipelines

