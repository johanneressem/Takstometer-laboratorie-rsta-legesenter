name: Deploy Voila App

on:
  push:
    branches:
      - main  # Kjør workflowen når noe push'es til main branch

jobs:
  build-deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Sjekk ut repoet
      uses: actions/checkout@v2

    - name: Sett opp Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.8'

    - name: Installer avhengigheter
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    - name: Distribuer med Voila
      run: |
        pip install jupyter-server==1.11
        voila --no-browser --port=8888
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
