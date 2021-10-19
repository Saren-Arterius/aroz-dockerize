# aroz-dockerize
Docker support for https://github.com/tobychui/arozos v1.116

# Usage
1. Ensure docker && docker-compose installed
2. Clone/Download this repo
3. If you are running on Intel/AMD machine then you can go to #5.
4. If you are running on ARM64 then you must edit the FROM line in /buildlocal/Dockerfile to FROM docker pull ghcr.io/dwilliamhouston/aroz-dockerize:master@sha256:213e1d1029da8d142e4492ad67ef74c5ebbbac9c2c99400d91e719c39c2df75b then save the file and go to #5
5. `$ docker-compose up`
6. Open http://localhost:8888/
