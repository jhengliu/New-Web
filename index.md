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
![GitHub Logo](https://lh3.googleusercontent.com/0GWU3a1kRvrnFRirq3s3L4UclvRaNdhurffuK5mTGReJgXeveqhA4Nw4SVtqdmjsox-xRoVNbWU4Vy28jCBQJ1Nx7go2cmpLjkd-cnf_L4wb1jqATVg3qH7bW8AGT_1ntBgHYsrj69dhfp1Qd8nx4ub7saDhbUBeGE5FRlEZFD4blRfiDeKGqVJ_tLI7rDcpBGyuT-sFG5UhxgnkhbY6TSO2xu22-0U9GGn75ZY3ZeSGNgG98lhiaU4-hw38jzFYASvupSkWm4ZtYWxGp6EGyzIi9eUbAtGmgyiEuaer5gR9XsBv7TbiYPXpMdl3uORbNsEnlbLreR5wVjcM53-Gc09RRMjeztjukv2lWSdl0ToA1RdkG_oTKgWoe1i_EE-1wyhM09OamJlghWsEQucKZ0jgzCmLtJBbkYZP3GamlGetAnAibBbZT8TnrTxctiIO_veDS9Hi6kGecrAOlMtKnzFDgo9DYDgh5tt4aXj_BzIiA2WywmjNKPwpI3uOUg3YM1rYp1eQWdhQwAOjfmVKbqH7X_BZ6oTlEQ7NT70o7JXqwnwBztKrISiYbf9pLzuGg2xHYNy-fu9JqrcCmrK-DXVQK3w2fM5z8fYHrfM=w1350-h1012-no)

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
