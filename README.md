# 南京四天三晚 · 秋日慢游（公开分享版）

适用于 GitHub Pages 的纯静态旅行网站，不需要 Node、后端服务器或 API Key。

## 部署到 GitHub Pages

1. 在 GitHub 创建一个新的公开仓库（例如 `nanjing-autumn-trip`）。
2. 将 `index.html`、`.nojekyll` 和 `assets/` 整个目录上传至仓库根目录。
3. 打开仓库 `Settings → Pages`，选择 `Deploy from a branch`，分支 `main`、目录 `/(root)`，保存。
4. 发布成功后通过 `https://<your-username>.github.io/nanjing-autumn-trip/` 访问。

## 功能

- 2026 年 10 月 26—29 日四日行程、每日图片与交通攻略。
- 在线 MapLibre / OpenFreeMap 地图（需要可访问第三方 CDN 与在线底图）；在服务无法加载时保留离线位置示意图。
- 公共景点高德搜索入口；路线线段为游览顺序示意，并非真实道路导航。
- 住宿固定为1间、3晚共1065元；可选秦淮画舫预算试算、可本地保存的预约勾选。

## 隐私规则

**这个公开部署包刻意不包含住宿的具体位置。** 不要把住宿门牌、楼栋、房号、经纬度、含详细地址的高德分享链接或私人行程截图提交到公开仓库；也不要将详细地址写入 Git 提交历史、README、图片说明、源码或网站脚本。住宿与机场/景点之间的导航请在私人地图里使用。

## 注意

- 根据 Gitee 官方帮助中心，Gitee Pages / Pages Pro 功能已下线，建议优先 GitHub Pages；若访问海外地图服务不稳定，可用静态网站托管的其他平台，在线地图仍依赖第三方可达性。
- 开放时间、地铁信息、景区观光车和游船票价请以运营方当日公告为准。

在线地图数据来源：OpenFreeMap / OpenStreetMap；实际道路路线请在高德导航核对。所有页面图像为示意插画，非实时实景。

## V2.2 坐标修正（2026-10-22）

- 修复 V2.1 的严重日期索引错误：D1 误画 D2，D2 误画 D3，D3 误画 D4，D4 会报错。统一 `DATA.days[selectedDay - 1]`。
- 修正了 V2.1 中多处坐标漂移的景点点位：鸡鸣寺、解放门、老门东、夫子庙、中山陵、音乐台、美龄宫、石象路、南博、总统府、1912及纪念馆。
- OpenFreeMap / MapLibre 使用 **WGS84**，所有经纬度统一按 WGS84 存储；部分只有高德 GCJ-02 数据的地点已转换，属于近似位置。
- 重要：明孝陵标记表示 **石象路神道**，并非明孝陵陵墓最北侧的主体位置。
- 在线地图在可正常测量大小的容器中初始化；加载成功后执行 resize 和日程数据重绘。
- 离线图仅表示点位大致分布，移除旧版本不准确的虚构河流和道路图形。
- 在线地图访问与瓦片显示需在能访问 MapLibre CDN / OpenFreeMap 的真实网络环境中验证；静态自动化测试不等于线上底图真实加载成功。

坐标校准参考：OpenStreetMap（Mapcarta）、Wikimedia Commons GPS、中山陵和石象路的高德公共 POI（仅用于公共景点坐标转换）。
- https://mapcarta.com/W319055520 （鸡鸣寺）
- https://mapcarta.com/W319998727 （南京博物院）
- https://mapcarta.com/W141915419 （音乐台）
- https://mapcarta.com/W338667850 （美龄宫）
- https://mapcarta.com/W62353727 （总统府）
- https://mapcarta.com/W992979424 （遇难同胞纪念馆史料陈列厅）
- https://mapcarta.com/W857492847 （1912街区）
- https://ditu.amap.com/place/B0019095PK （玄武湖解放门）
- https://ditu.amap.com/place/B00190BU4S （老门东）
- https://ditu.amap.com/place/B00190ANHZ （南京夫子庙）
- https://ditu.amap.com/place/B001909J40 （明孝陵石象路神道）

注意：仓库中不存储住宿的完整地址或精确坐标。

离线模式显示的是每天的景点**顺序图**，不再使用容易让人误以为真实的虚构地理底图。

## 更新住宿预算（2026-10-22）

- 住宿：1间、3晚，共1065元。
- 两人参考总预算（不含机票）：不乘船2615–3645元；选择画舫2815–3845元。
- 交通和时间安排均为参考估计，不是实时导航；从住宿点出发的具体导航以实际位置为准。

## 后续更新

站点启用 GitHub Pages 的 `main` 分支、`/(root)` 发布后，修改 `index.html` 或 `assets/` 并提交到 `main`，GitHub 会重新发布；分享网址保持不变。发布前复查住宿隐私，勿上传项目外的原始行程 Markdown、系统文件或私人截图。

发布目录仅包含站点 HTML、README、`.nojekyll`、`.gitignore` 和 `assets/`。没有构建步骤，公开仓库文件与站点文件一致。在线地图仍依赖 CDN 和 OpenFreeMap 的网络可用性；不能据此保证所有中国大陆网络均可访问。
