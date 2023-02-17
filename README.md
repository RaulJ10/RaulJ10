

name: GitHub-Profile-3D-Contrib

on:
  schedule: # 03:00 JST == 18:00 UTC
    - cron: "0 18 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v3
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          git commit -m "generated"
          git push

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=RaulJ10&theme=algolia&show_icons=true)

[![GitHub Streak](http://github-readme-streak-stats.herokuapp.com?user=RaulJ10&theme=algolia&hide_border=FALSO&mode=weekly&disable_animations=FALSO)](https://git.io/streak-stats)
