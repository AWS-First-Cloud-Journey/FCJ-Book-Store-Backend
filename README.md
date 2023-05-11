#### Install Python 3.9

wget https://www.python.org/ftp/python/3.9.9/Python-3.9.9.tgz
tar -xf Python-3.9.9.tgz
cd Python-3.9.9
./configure --enable-optimizations
sudo make altinstall


#### Deploy Backend Services

git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Book-Store-Backend.git
cd FCJ-Book-Store-Backend

sam build
sam deploy --guided

****Note: Thay API****

#### Deploy Frontend Service

git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-Workshop.git
cd FCJ-Serverless-Workshop
npm install --force
npm install --global yarn
yarn build
aws s3 cp build s3://fcj-book-store-2000 --recursive
