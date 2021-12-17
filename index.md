# Laurence's IT Playground

## ML Toys
* https://github.com/mf523/video-stream-bridge

## Examples
* [Build GAN (Generative Adversarial Networks) with PyTorch and SageMaker](https://github.com/aws/amazon-sagemaker-examples/blob/master/advanced_functionality/pytorch_bring_your_own_gan/build_gan_with_pytorch.ipynb)

## Blogs
* [轻松构建 PyTorch 生成对抗网络](https://aws.amazon.com/cn/blogs/china/easily-build-pytorch-generative-adversarial-networks-gan/) 
* [Build GAN with PyTorch and Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/build-gan-with-pytorch-and-amazon-sagemaker/)
* [配置Aurora数据库，整合KMS的静态加密 (Aurora static encryption with KMS)](https://aws.amazon.com/cn/blogs/china/defense-depth-aws-data-how-to-configure-aurora-integrate-kms-static-encryptio/)

## How to upload contents in big zip file to AWS S3 bucket without uncompressing
```python
#!/bin/env python

import sys
from zipfile import ZipFile
import boto3

def main(zipfile_path, bucket, prefix):
    s3 = boto3.resource('s3')

    with ZipFile(zipfile_path, 'r') as zip:
        # printing all the contents of the zip file
        for f in zip.namelist():
            if not zip.getinfo(f).is_dir():
                obj = s3.Object(bucket, f"{prefix}/{f}")
                obj.put(Body=zip.read(f))
                print(f"uploaded s3://{bucket}/{prefix}/{f}")
        print('Done!')

if __name__ == "__main__":
    main(zipfile_path=sys.argv[1], bucket=sys.argv[2], prefix=sys.argv[3])
```

## Install WSL on Windows Server 2019
* https://docs.microsoft.com/en-us/windows/wsl/install
* https://docs.microsoft.com/en-us/windows/wsl/install-on-server
* https://computingforgeeks.com/run-linux-on-windows-server/
* https://community.chocolatey.org/packages/wsl-ubuntu-2004
* https://docs.docker.com/desktop/windows/wsl/
* https://www.public-health.uiowa.edu/it/support/kb48568/
