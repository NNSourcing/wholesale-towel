# 毛巾批发独立站（Decap CMS + GitHub + Netlify）

## 文件说明
- `index.html`：前台网站，从 `data/products.json` 读取商品
- `data/products.json`：商品数据（后台保存时会自动改这个文件）
- `admin/index.html`、`admin/config.yml`：商品管理后台
- `images/uploads/`：后台上传的图片会存到这里

## 部署步骤
1. 在 GitHub 新建仓库（建议选 Private），把整个文件夹上传。
2. 打开 `admin/config.yml`，把 `repo:` 改成 `你的用户名/仓库名`，提交。
3. Netlify：Add new site → Import from Git → 选这个仓库。Build command 留空，Publish directory 填 `.`。
4. GitHub：Settings → Developer settings → OAuth Apps → New OAuth App
   - Homepage URL：你的 Netlify 网址
   - Authorization callback URL：`https://api.netlify.com/auth/done`
   - 创建后复制 Client ID，并生成 Client secret
5. Netlify：Site configuration → Access control → OAuth → Install provider → 选 GitHub，填入 Client ID 和 Secret。
6. 打开 `https://你的网址/admin`，用 GitHub 登录，就能管理商品。

## 只有你能登录
后台用 GitHub 账号登录，只有对这个仓库有写权限的账号才能保存商品。
- 不要把别人加为仓库协作者
- 仓库设为 Private
- 给你的 GitHub 账号开启两步验证（2FA）

## 日常使用
后台 → 商品管理 → 商品列表 → 添加/编辑商品 → Publish。
几十秒后 Netlify 自动重新部署，前台就会更新。
Status 选“下架”，该商品就不会在前台显示。

## 修改联系方式
在 `index.html` 里找到 `EMAIL` 和 `WHATSAPP` 两行修改。

## 本地预览
直接双击打开 `index.html` 读不到商品数据，需要起一个本地服务：
`python3 -m http.server 8000`，然后访问 http://localhost:8000
