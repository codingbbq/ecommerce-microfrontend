# Understanding Microfrontends Course

## Below steps to consider
1) Designate one app as the Host and other as the Remote
2) In the Remote, decide which modules you want to make available to other projects
3) Set up Module federation plugin to expose those files
4) In the host, decide which files you want to get from the remote
5) Set up Module federation plugin to fetch those files
6) In the host, refactor the entry point to load asynchronously
7) In the host, import whatever files you need from the remote

## Using shared modules
1) Container fetches Products remoteEntry.js file
2) Container fetches Cart remoteEntry.js file
3) Container notices that both require Faker
4) Container can choose to load only one copy from either Cart of Products
5) Single Copy is made available to both Cart + Products

## How to Run the application
1) `container` is the folder that is the host that contains all MFEs
2) `produts` is one MFE that shows list of products. It is hosted on port 8081
3) `cart` is another MFE that shows the cart details. It is hosted on port 8082
4) `container` being the host is is hosted on port 8080 and it calls the entire .js code from individual MFEs as remoteEntry.js
5) Important code to look at is `webpack.config.js` of each individual MFEs
