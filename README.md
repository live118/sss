<!DOCTYPE html>
<html>
<head>

<script>
window.onload=function()
{
	var genders=document.getElementsByName("gender");
	var grades=document.getElementsByName("grade");
	var input=document.getElementsByTagName("input");
	var box = document.getElementById("box");
	var memo ="";
	
	input[input.length-1].onclick=function(){
		if(memo==""){
			var str="";
			if(genders[0].checked==true){
				if(grades[0].checked==true){
					str="<h1>1학년 남성입니다.</h>";
				}else if(grades[1].checked==true){
					str="<h1>2학년 남성입니다.</h>";
				}else {
					str="<h1>3학년 남성입니다.</h>";
				}
			}else{
					if(grades[0].checked==true){
						str="<h1>1학년 여성입니다.</h>";
					}else if(grades[1].checked==true){
						str="<h1>2학년 여성입니다.</h>";
					}else {
						str="<h1>3학년 여성입니다.</h>";
					}
			}
			box.removeChild(this);
			memo=box.innerHTML;
			box.innerHTML=str;
			box.appendChild(this);
		}else{
			box.innerHTML=memo;
			box.appendChild(this);
			memo="";
		}
	}
}
	
</script>

<meta charset = "EUC-KR">
</head>
<body>

<div id = "box" >
	<h3>성별은 무엇인가요?</h3>
	<input type="radio" name="gender" value="M" checked />
	<input type="radio" name="gender" value="F"  />
	<br/>
	<h3>몇 학년인가요?</h3>
	<input type = "radio" name="grade" value="1" checked />
	<input type = "radio" name="grade" value="2" />
	<input type = "radio" name="grade" value="3" />
	<br/>
	<input type="button" value ="확인"/>
	
</div>
</body>
</html>
