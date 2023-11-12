# Docker指令集

## 簡介

紀錄Docker常用指令


## 目錄
- [Docker指令集](#docker指令集)
  - [簡介](#簡介)
  - [目錄](#目錄)
    - [Docker Service](#docker-service)
    - [Docker Container](#docker-container)
    - [Docker Image](#docker-image)
    - [Docker run 常用語法集合](#docker-run-常用語法集合)
    - [補充:如何刪除多個Image](#補充如何刪除多個image)


### Docker Service

|  指令   | 說明  |
| :----:  | :----: |
| docker version  | 查看Docker版本資訊 |
| service docker status  | 查看Docker目前狀態 |
| service docker start  | 啟動Docker Service |
| service docker restart  | 將Docker Service重啟 |
| service docker stop  | 將Docker Service停止 |


### Docker Container
|  指令   | 說明  |
| :----:  | :----: |
| docker ps、docker container ls  | 列出執行中Container |
| docker ps -a 、docker container ls -a | 列出未執行狀態的Container |
| docker attach <name or id> | 連接到一個執行中容器的輸出(顯示容器) |
| docker exec -it <name or id> <Command> | 在 Container 上執行命令 |


### Docker Image
|  指令   | 說明  |
| :----:  | :----: |
| docker images、docker image ls  | 列出所有映像檔 |
| docker ps -a  | 列出未執行狀態的Container |
| docker rmi <name or id> | 刪除映像檔 |
| docker pull <Image URI> | 預設抓取官方來源(DockerHub) |

### Docker run 常用語法集合

```docker
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

```docker
-a：就是--attach，執行時接上輸出

-c or --cpu-shares：分配cpu，多容器時使用

-d：背景執行，必須是automated才有用

-e：設定環境變數

-it：進入容器的shell中

-p：指定主機對應的通訊埠到容器的通訊埠中

-v：指定volume或對應目錄

-w：指定容器內工作目錄

--name:指定容器名稱

--rm：執行完後直接刪除。

```

### 補充:如何刪除多個Image

> 請使用PowerShell或是GitBash進行刪除，cmd因不支援Linux指令會導致出錯

請輸入以下語法
```docker
docker rmi $(docker images -aq) -f
```

![image-20231112144022696](https://raw.githubusercontent.com/Mark850409/UploadGithubImage/master/image-20231112144022696.png)


