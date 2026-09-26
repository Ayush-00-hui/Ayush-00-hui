name: 3D Contribution Skyline

on:
  schedule:
    - cron: "0 3 * * *"   # once a day
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Generate 3D skyline
        uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          username: Ayush-00-hui

      - name: Commit and push
        run: |
          git config user.name "github-actions"
          git config user.email "actions@github.com"
          git add -f profile-3d-contrib/*.svg
          git commit -m "chore: update 3d contribution skyline" || echo "nothing to commit"
          git push
