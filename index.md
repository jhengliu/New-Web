## Welcome to GitHub Pages

You can use the [editor on GitHub](https://www.youtube.com/watch?v=JwjBbWQs71k) to maintain and preview the content for your website in Markdown files.
https://github.com/jhengliu/tee/edit/master/index.md
Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

For more details see [youtube](https://www.youtube.com/watch?v=JwjBbWQs71k).
![GitHub Logo](https://scontent.ftpe3-1.fna.fbcdn.net/v/t1.0-9/13177341_883733221755348_3788928508532700048_n.jpg?oh=d8da7efc5756c123e4662041b274e70e&oe=5ABBF33A)

## 我們一起來錄音～
![GitHub Logo](https://scontent.ftpe3-1.fna.fbcdn.net/v/t1.0-9/13335578_894160290712641_8066235228498622809_n.jpg?oh=0dcb05483f0c3218baf547196cc7f83d&oe=5AEE155E)

public static void main(String[] args) throws IOException {
    YouTube youtube = getYouTubeService();
    try {
        HashMap<String, String> parameters = new HashMap<>();
        parameters.put("part", "snippet,contentDetails");
        parameters.put("channelId", "UC_x5XG1OV2P6uZZ5FSM9Ttw");
        parameters.put("maxResults", "25");

        YouTube.Activities.List activitiesListRequest = youtube.activities().list(parameters.get("part").toString());
        if (parameters.containsKey("channelId") && parameters.get("channelId") != "") {
            activitiesListRequest.setChannelId(parameters.get("channelId").toString());
        }

        if (parameters.containsKey("maxResults")) {
            activitiesListRequest.setMaxResults(Long.parseLong(parameters.get("maxResults").toString()));
        }

        ActivityListResponse response = activitiesListRequest.execute();
        System.out.println(response);
    }
}

東水 | 東中
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

<?php
namespace App\Providers;
use Illuminate\Support\ServiceProvider;
class YouTubeServiceProvider extends ServiceProvider
{
  /**
    * Bootstrap the application services.
    *
    * @return void
    */
  public function boot()
  {
    //
  }
  /**
    * Register the application services.
    *
    * @return void
    */
  public function register()
  {
    $app = $this->app;
    $this->app->bind('GoogleClient', function () {
      $googleClient = new \Google_Client();
      $googleClient->setAccessToken(\Session::get("google_token"));
      return $googleClient;
    });
    $this->app->bind('YoutubeClient', function () use ($app) {
      $googleClient = \App::make('GoogleClient');
      $youtube = new \Google_Service_YouTube($googleClient);
      return $youtube;
    });
  }
}

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/jhengliu/tee/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
