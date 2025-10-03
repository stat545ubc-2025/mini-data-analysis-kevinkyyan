Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## Warning: package 'ggplot2' was built under R version 4.5.1

    ## Warning: package 'purrr' was built under R version 4.5.1

    ## Warning: package 'stringr' was built under R version 4.5.1

    ## Warning: package 'forcats' was built under R version 4.5.1

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.1     ✔ stringr   1.5.2
    ## ✔ ggplot2   4.0.0     ✔ tibble    3.3.0
    ## ✔ lubridate 1.9.4     ✔ tidyr     1.3.1
    ## ✔ purrr     1.1.0     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2024>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/158528/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2024 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R.html)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: *cancer_sample* 2: *parking_meters* 3: *parking_meters* 4:
*vancouver_trees*

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

# Using glimpse function to explore the variables avaialbe, number of rows, and columns

``` r
glimpse (steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
glimpse(cancer_sample)
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

``` r
glimpse (parking_meters)
```

    ## Rows: 10,032
    ## Columns: 22
    ## $ meter_head     <chr> "Twin", "Pay Station", "Twin", "Single", "Twin", "Twin"…
    ## $ r_mf_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_mf_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_sa_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_sa_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_su_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_su_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ rate_misc      <chr> NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ time_in_effect <chr> "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFEC…
    ## $ t_mf_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_mf_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_sa_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_sa_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_su_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_su_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ time_misc      <chr> NA, "No Time Limit", NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ credit_card    <chr> "No", "Yes", "No", "No", "No", "No", "No", "No", "No", …
    ## $ pay_phone      <chr> "66890", "59916", "57042", "57159", "51104", "60868", "…
    ## $ longitude      <dbl> -123.1289, -123.0982, -123.1013, -123.1862, -123.1278, …
    ## $ latitude       <dbl> 49.28690, 49.27215, 49.25468, 49.26341, 49.26354, 49.27…
    ## $ geo_local_area <chr> "West End", "Strathcona", "Riley Park", "West Point Gre…
    ## $ meter_id       <chr> "670805", "471405", "C80145", "D03704", "301023", "5913…

``` r
glimpse (vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

# Using summarise function to look at the class of the data variables

``` r
steam_games%>%
  summarise(across(everything(), class))
```

    ## # A tibble: 1 × 21
    ##   id      url   types name  desc_snippet recent_reviews all_reviews release_date
    ##   <chr>   <chr> <chr> <chr> <chr>        <chr>          <chr>       <chr>       
    ## 1 numeric char… char… char… character    character      character   character   
    ## # ℹ 13 more variables: developer <chr>, publisher <chr>, popular_tags <chr>,
    ## #   game_details <chr>, languages <chr>, achievements <chr>, genre <chr>,
    ## #   game_description <chr>, mature_content <chr>, minimum_requirements <chr>,
    ## #   recommended_requirements <chr>, original_price <chr>, discount_price <chr>

``` r
cancer_sample%>%
  summarise(across(everything(), class))
```

    ## # A tibble: 1 × 32
    ##   ID      diagnosis radius_mean texture_mean perimeter_mean area_mean
    ##   <chr>   <chr>     <chr>       <chr>        <chr>          <chr>    
    ## 1 numeric character numeric     numeric      numeric        numeric  
    ## # ℹ 26 more variables: smoothness_mean <chr>, compactness_mean <chr>,
    ## #   concavity_mean <chr>, concave_points_mean <chr>, symmetry_mean <chr>,
    ## #   fractal_dimension_mean <chr>, radius_se <chr>, texture_se <chr>,
    ## #   perimeter_se <chr>, area_se <chr>, smoothness_se <chr>,
    ## #   compactness_se <chr>, concavity_se <chr>, concave_points_se <chr>,
    ## #   symmetry_se <chr>, fractal_dimension_se <chr>, radius_worst <chr>,
    ## #   texture_worst <chr>, perimeter_worst <chr>, area_worst <chr>, …

``` r
parking_meters%>%
  summarise(across(everything(), class))
```

    ## # A tibble: 1 × 22
    ##   meter_head r_mf_9a_6p r_mf_6p_10 r_sa_9a_6p r_sa_6p_10 r_su_9a_6p r_su_6p_10
    ##   <chr>      <chr>      <chr>      <chr>      <chr>      <chr>      <chr>     
    ## 1 character  character  character  character  character  character  character 
    ## # ℹ 15 more variables: rate_misc <chr>, time_in_effect <chr>, t_mf_9a_6p <chr>,
    ## #   t_mf_6p_10 <chr>, t_sa_9a_6p <chr>, t_sa_6p_10 <chr>, t_su_9a_6p <chr>,
    ## #   t_su_6p_10 <chr>, time_misc <chr>, credit_card <chr>, pay_phone <chr>,
    ## #   longitude <chr>, latitude <chr>, geo_local_area <chr>, meter_id <chr>

``` r
vancouver_trees%>%
  summarise(across(everything(), class))
```

    ## # A tibble: 1 × 20
    ##   tree_id civic_number std_street genus_name species_name cultivar_name
    ##   <chr>   <chr>        <chr>      <chr>      <chr>        <chr>        
    ## 1 numeric numeric      character  character  character    character    
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <chr>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <chr>,
    ## #   diameter <chr>, curb <chr>, date_planted <chr>, longitude <chr>,
    ## #   latitude <chr>

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

The cancer sample dataset as I currently work in health services
research and am interested in cancer research
<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

What is the relationship between cancer area and diagnosis?
<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.

``` r
ggplot(cancer_sample, aes(x = area_mean)) +
  geom_histogram(bins = 100, fill = "black", color = "white") +
  labs(title = "Distribution of Area of Sample",
       x = "Area",
       y = "Count")
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

2.  Investigate how many missing values there are per variable. Can you
    find a way to plot this? No missing varaibles were identified

``` r
unique(cancer_sample$diagnosis)
```

    ## [1] "M" "B"

``` r
unique(cancer_sample$area_mean)
```

    ##   [1] 1001.0 1326.0 1203.0  386.1 1297.0  477.1 1040.0  577.9  519.8  475.9
    ##  [11]  797.8  781.0 1123.0  782.7  578.3  658.8  684.5  798.8 1260.0  566.3
    ##  [21]  520.0  273.9  704.4 1404.0  904.6  912.7  644.8 1094.0  732.4  955.1
    ##  [31] 1088.0  440.6  899.3 1162.0  807.2  869.5  633.0  523.8  698.8  559.2
    ##  [41]  563.0  371.1 1104.0  545.2  531.5 1076.0  201.9  534.6  449.3  561.0
    ##  [51]  427.9  571.8  437.6 1033.0  712.8  409.0 1152.0  656.9  527.2  224.5
    ##  [61]  311.9  221.8  645.7  260.9  499.0  668.3  269.4  394.1  250.5  502.5
    ##  [71] 1130.0  244.0  929.4  584.1  470.9  817.7 1006.0 1245.0  506.3  401.5
    ##  [81] 1878.0 1132.0  443.3 1075.0  648.2  466.1  651.9  662.7  728.2  551.7
    ##  [91]  555.1  705.6 1264.0  451.1  294.5  412.6  642.5  582.7  143.5  458.7
    ## [101]  298.3  336.1  530.2  412.5  466.7 1509.0  396.5  290.2  480.4  629.9
    ## [111]  334.2  230.9  438.6  245.2  682.5  782.6  982.0  403.3 1077.0 1761.0
    ## [121]  640.7  553.5  588.7  572.6 1138.0  674.5 1192.0  455.8  748.9  809.8
    ## [131]  761.7  423.6  399.8  678.1  384.8  288.5  813.0  398.0  512.2  355.3
    ## [141]  432.8  432.0  689.5  640.1  585.0  519.4  203.9  300.2  381.9  538.9
    ## [151]  460.3  963.7  880.2  448.6  366.8  419.8 1157.0 1214.0  464.5 1686.0
    ## [161]  690.2  357.6  886.3  984.6  685.9  464.1  565.4  736.9  372.7  349.6
    ## [171]  227.2  302.4  832.9  526.4  508.8 2250.0 1311.0  766.6  402.0  710.6
    ## [181]  317.5 1041.0  420.3  428.9  463.7  609.9  507.4  288.1  477.4  671.4
    ## [191]  516.4  588.9 1024.0 1148.0  642.7  461.0  951.6 1685.0  597.8  481.9
    ## [201]  716.6  295.4  904.3  529.4  725.5 1290.0  428.0 2499.0  948.0  610.7
    ## [211]  578.9  432.2  321.2 1230.0 1223.0  568.9  561.3  313.1  761.3  546.4
    ## [221]  641.2  329.6  496.4  503.2  895.0  395.7  386.8 1319.0  279.6  603.4
    ## [231] 1670.0 1306.0  623.9  920.6  575.3  476.5  389.4  590.0 1155.0  337.7
    ## [241]  541.6  347.0  406.3 1364.0  407.4 1206.0  928.2 1169.0  602.4 1207.0
    ## [251]  713.3  773.5  744.9 1288.0  933.1  947.8  758.6  928.3 1419.0  346.4
    ## [261]  344.9  632.6  388.0 1491.0  289.9  998.9  435.6  396.6 1102.0  572.3
    ## [271]  587.4  427.3 1145.0  805.1  516.6  489.0  441.0  515.9  396.0  651.0
    ## [281]  687.3  513.7  432.7  492.1  363.7  431.1  633.1 1217.0  471.3 1247.0
    ## [291]  334.3  403.1  417.2  537.3  246.3  566.2  530.6  418.7  664.9  504.1
    ## [301]  409.1  221.2  481.6  461.4 1027.0  244.5  477.3  324.2 1274.0  504.8
    ## [311]  457.9  489.9  616.5  446.0  813.7  826.8  793.2  514.0  387.3  390.0
    ## [321]  464.4  918.6  514.3 1092.0  310.8 1747.0  280.5  373.9 1194.0  321.6
    ## [331]  445.3  668.7  402.7  426.7  421.0 2010.0  384.6  485.8  512.0  593.7
    ## [341]  241.0  278.6  491.9  546.1  496.6  838.1  552.4 1293.0 1234.0  458.4
    ## [351] 1546.0 1482.0  840.4  711.8 1386.0 1335.0  579.1  788.5  338.3  562.1
    ## [361]  580.6  361.6  386.3  447.8  462.9  541.8  664.7  462.0  596.6  392.0
    ## [371] 1174.0  234.3  744.7 1407.0  446.2  609.1  558.1  508.3  378.2  431.9
    ## [381]  994.0  442.7  525.2  507.6  469.1  370.0  800.0  514.5  991.7  373.2
    ## [391]  268.8  693.7  719.5  433.8  271.2  803.1  495.0  380.3  409.7  656.1
    ## [401]  408.2  289.7  307.3  333.6  359.9  381.1  501.3  685.0  467.8 1250.0
    ## [411] 1110.0  673.7  599.5  509.2  611.2  592.6  606.5  371.5  928.8  585.9
    ## [421]  340.9  990.0  441.3  981.6  674.8  659.7 1384.0 1191.0  442.5  644.2
    ## [431]  492.9  557.2  415.1  537.9  520.2  290.9  930.9 2501.0  646.1  412.7
    ## [441]  542.9  536.9  286.3  980.5  408.8  289.1  449.9  686.9  465.4  358.9
    ## [451]  506.9  618.4  599.4  404.9  815.8  455.3  602.9  546.3  571.1  747.2
    ## [461]  476.7  666.0 1167.0  420.5  857.6  466.5  992.1 1007.0  538.7  680.9
    ## [471]  485.6  480.1 1068.0 1320.0  689.4  595.9  476.3 1682.0  248.7  272.5
    ## [481]  453.1  366.5  819.8  731.3  426.0  680.7  556.7  701.9  391.2 1052.0
    ## [491]  493.1  493.8  257.8 1841.0  388.1  571.0  293.2  221.3  551.1  468.5
    ## [501]  594.2  445.2  422.9  416.2  575.5 1299.0  365.6 1308.0  629.8  406.4
    ## [511]  178.8  170.4  402.9  656.4  668.6  538.4  584.8  573.2  324.9  320.8
    ## [521]  285.7  360.5  378.4  507.9  264.0  321.4  311.7  271.3  657.1  403.5
    ## [531]  600.4  386.0  716.9 1347.0 1479.0 1261.0  858.1 1265.0  181.0

``` r
range (cancer_sample$area_mean)
```

    ## [1]  143.5 2501.0

3.  Explore the relationship between 2 variables in a plot.

``` r
ggplot(cancer_sample, aes(x = diagnosis, y = area_mean, fill = diagnosis)) +
  geom_boxplot() +
  labs(title = "Relationship Between Area and Diagnosis",
       x = "Diagnosis",
       y = "Mean Are") +
  scale_fill_discrete(labels = c("B" = "Benign", "M" = "Malignant"))
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

4.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.

``` r
cancer_analysis <- cancer_sample %>%
  select(diagnosis, area_mean)
```

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

1.  Plot the distribution of a numeric variable. This to understand if
    the data is skewed or not and to identify any potential outliers

2.  Investigate how many missing values there are per variable. Can you
    find a way to plot this? This would be good to explore, if there is
    many missing variables that could potentially bias the analysis

3.  Explore the relationship between 2 variables in a plot. This helps
    to answer the research question to visually look to see if there
    could be any potential correlation between area size and diagnosis

4.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring. This allows me to
    work with a dataset that’s smaller and more focused on only the
    variables that are required to answer the research question.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

1.  What is the relationship between radius size of cancer and
    diagnosis?
2.  What is the relationship between perimeter size of cancer and
    diagnosis?
3.  What is the relationship between smoothness and diagnosis?
4.  What is the relationship between texture and diagnosis?

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
