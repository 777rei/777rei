<div align="center">

  <!-- 1. THE HACKER HEADER -->
  <img src="https://herokuapp.com" alt="Typing SVG" />

  <br/>

  <!-- 2. TECH STACK (NEON ICONS) -->
  <img src="https://skillicons.dev" />

</div>

<br/>

<!-- 3. THE DASHBOARD (Stats + Spotify) -->
<table align="center">
  <tr>
    <td align="center" width="50%">
      <!-- GITHUB STATS (Cyberpunk Style) -->
      <img src="https://vercel.app" />
      <br/><br/>
      <img src="https://vercel.app" />
    </td>
    <td align="center" width="50%">
      <!-- SPOTIFY "NOW PLAYING" -->
      <!-- READ "STEP 3" BELOW TO MAKE THIS WORK! -->
      <a href="https://github.com">
        <img src="https://kittinanx.com" alt="Spotify" />
      </a>
    </td>
  </tr>
</table>

<!-- 4. THE 3D CITY (Requires Step 2 Below) -->
<div align="center">
  <h3>🏙️ My Contribution City</h3>
  <img src="https://github.com" alt="3D Profile" width="100%" />
</div>

<div align="center">
  <img src="https://komarev.com" alt="Profile Views" />
</div>

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

          
