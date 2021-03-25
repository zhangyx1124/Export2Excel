# Export2Excel
vue中 Export2Excel 将 table 导成 excel方法
1.安装依赖：

npm install -S file-saver
npm install -S xlsx
npm install -D script-loader
注意：如果页面中存在图中问题



 在webpack.base.conf.js 里面增加resolve下一行代码
‘vendor’: path.resolve(__dirname, ‘…/src/vendor’)



2.在项目中创建一个文件vendor，src目录下创建，把Blob.js和 Export2Excel.js这两个js放到新建的文件夹vendor内。

原文链接：https://blog.csdn.net/sky_sunshine_x/article/details/103138196
