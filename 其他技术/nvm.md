# nvm

显示所有可下载的node版本

nvm list  available

下载node

nvm install 版本号

显示已安装的版本

nvm list

删除node

nvm uninstall 版本号

切换版本

nvm use 版本号

显示当前node版本

nvm current

nvm 安装地址下的settings

root: D:\code\nvm path: D:\code\node

node_mirror:https://npmmirror.com/mirrors/node/ npm_mirror:https://npmmirror.com/mirrors/npm/

以下是一些常用的国内npm镜像源：

### 淘宝镜像

- **网址**：https://registry.npmmirror.com/.
- **配置命令**：`npm config set registry <https://registry.npmmirror.com/`>.
- **特点**：这是国内使用较为广泛的镜像源之一，由淘宝团队提供，数据更新及时，下载速度快，能满足大多数项目的依赖包下载需求.

### 阿里云镜像

- **网址**：https://registry.npm.alibaba-inc.com/.
- **配置命令**：`npm config set registry <https://registry.npm.alibaba-inc.com/`>.
- **特点**：依托阿里云的强大基础设施，稳定性高，对于在阿里云服务器上部署的项目或使用阿里云相关服务的开发者来说，是个不错的选择.

### 腾讯云镜像

- **网址**：https://mirrors.cloud.tencent.com/npm/.
- **配置命令**：`npm config set registry <https://mirrors.cloud.tencent.com/npm/`>.
- **特点**：在华南等地区的访问速度有优势，为腾讯云用户及周边地区的开发者提供了稳定快速的下载服务.

### 华为云镜像

- **网址**：https://repo.huaweicloud.com/repository/npm/.
- **配置命令**：`npm config set registry <https://repo.huaweicloud.com/repository/npm/`>.
- **特点**：适合使用华为云服务的开发者，其网络优化和服务器性能能够保障依赖包的高效下载，在华为云生态体系内具有良好的兼容性.

### 中国科学技术大学镜像

- **网址**：https://npm.mirrors.ustc.edu.cn/ 或 https://mirrors.ustc.edu.cn/npm/.
- **配置命令**：`npm config set registry <https://npm.mirrors.ustc.edu.cn/`> 或 `npm config set registry <https://mirrors.ustc.edu.cn/npm/`>.
- **特点**：教育网内访问速度快，对于高校师生及科研机构的开发者，尤其是在中科大及其周边网络环境的用户，使用体验较好.

### 清华大学镜像

- **网址**：https://mirrors.tuna.tsinghua.edu.cn/npm/.
- **配置命令**：`npm config set registry <https://mirrors.tuna.tsinghua.edu.cn/npm/`>.
- **特点**：在华北和华东地区等教育网覆盖区域访问速度出色，镜像源的维护和数据同步较为稳定，是高校和科研机构常用的镜像源之一.