<p>
    <img src="https://github-readme-stats.vercel.app/api?username=theunusualdev&show_icons=true&count_private=true&include_all_commits=false&text_color=000000&bg_color=45,ff0000,0000ff&ring_color=00fb10&border_color=000000" alt="My details" align="left" height="150px"/>
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=theunusualdev&langs_count=3&theme=dark&layout=compact&border_color=000000" alt="Most used languages" align="right" height="150px"/>
  </p>
    <img src="images/userstats.svg" alt="user stats" align="center"/>
    name: user-statistician

on:
  schedule:
    - cron: '0 3 * * *'
  workflow_dispatch:

jobs:
  stats:
    runs-on: ubuntu-latest
      
    steps:
    - uses: actions/checkout@v2

    - name: Generate the user stats image
      uses: cicirello/user-statistician@v1
      with:
        colors: dark-dimmed
        custom-title: My GitHub Statistics
        max-languages: 100
        hide-keys: 'languages'
      env:
        GITHUB_TOKEN: ${{secrets.GITHUB_TOKEN}}
