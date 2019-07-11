# JS-Ajax

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>demo</title>
</head>
<body>
        <form>

        <button onclick="returnText();return false">登陆</button>
    </form>
    <script type="text/javascript">
        function returnText(){
            var xhr = createXHR();
            xhr.onreadystatechange = function(){
                if(xhr.readyState == 4){
                    if((xhr.status >= 200 && xhr.status < 300) || xhr.status == 304){
                        alert(xhr.responseText);
                    }else{
                        alert('获取失败'+xhr.status)
                    }
                }
            }
            xhr.open('get','demo.php',true);
            xhr.send(null);

        }
        function createXHR(){
            if(typeof XMLHttpRequest != 'undefined'){
                return new XMLHttpRequest();
            }else{
                return new ActiveXObject('Microsoft.XMLHTTP')
            }
        }
    </script>
</body>
</html>
