<%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>
<%@ page import="java.awt.image.BufferedImage" %>
<%@ page import="java.awt.Graphics"%>
<%@ page import="javax.imageio.ImageIO;" %>
<html>
<head>
<title>My JSP 'index.jsp' starting page</title>
</head>
<body>
<%
BufferedImage image = new BufferedImage(130,30,BufferedImage.TYPE_INT_RGB);
Graphics g = image.getGraphics();
g.drawString("hello word!", 10, 20);
g.dispose();
ServletOutputStream responseOutputStream =response.getOutputStream();
// 输出图象到页面
ImageIO.write(image, "JPEG", responseOutputStream);
//以下关闭输入流！
responseOutputStream.flush();
responseOutputStream.close();
out.clear();
out = pageContext.pushBody();
%>
</body>
</html>
