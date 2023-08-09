---
title: 相册
date: 2023-08-07 22:33:47
comments: false
---
{% raw %}
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>相册页面</title>
  <link rel="stylesheet" href="../lib/test_album/ins.css">
  <link rel="stylesheet" href="../lib/test_album/photoswipe.css"> 
  <link rel="stylesheet" href="../lib/test_album/default-skin/default-skin.css">
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script> <!-- 引入 jQuery -->
  <script src="../lib/test_album/ins.js"></script> <!-- 引入 ins.js -->
</head>
<body>

<div class="instagram itemscope">
    <a href="https://xiryg.github.io" target="_blank" class="open-ins">图片正在加载中…</a>
</div>

<script>
  // 检查页面是否需要刷新并显示提示
  var postTitle = document.querySelector('.post-title');
  if (postTitle) {
    // 获取 localStorage 中的标记变量值
    var needRefresh = localStorage.getItem('needRefresh');
    
    // 检查标记变量值
    if (needRefresh === 'true') {
      // 显示提示
      var message = document.createElement('div');
      message.innerHTML = '图片加载完成，页面将在2秒后刷新';
      message.style.position = 'fixed';
      message.style.top = '50%';
      message.style.left = '50%';
      message.style.transform = 'translate(-50%, -50%)';
      message.style.backgroundColor = 'rgba(0, 0, 0, 0.7)';
      message.style.color = 'white';
      message.style.padding = '10px';
      message.style.borderRadius = '5px';
      document.body.appendChild(message);
      
      // 刷新页面
      setTimeout(function() {
        location.reload();
      }, 2000);
      
      // 将标记变量值设置为 false
      localStorage.setItem('needRefresh', 'false');
    }
  } else {
    // 退出页面时将标记变量值设置为 true
    localStorage.setItem('needRefresh', 'true');
  }
</script>

</body>
</html>

{% endraw %}

