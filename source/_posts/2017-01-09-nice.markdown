---
layout: post
title: "hello world"
date: 2017-01-09 17:20:49 +0800
comments: true
categories: [Ruby,Java]
---
# hello world
## You will learn what you want

**bold**

`LIGHTED`

- Ruby
   - TEST
   - Develop
- Java
- HTML

>Reference

[WikiDemo](https://en.wikipedia.org/wiki/Main_Page)

![imageDemo](http://img1.cache.netease.com/catchpic/5/5B/5BAD5D92CA03AA221A513800CC0A420C.jpg)

```java  This is used in Servlet
package com.whut.servlet;

import java.io.IOException;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class LoginServlet extends HttpServlet {

	/**
	 * 
	 */
	//用于序列化和反序列化
	private static final long serialVersionUID = 4426037562056379764L;

	/*@Override
	protected void service(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);
	}*/

	@Override
	protected void doGet(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		/*System.out.println("=====进入doGet方法=====");
		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);*/
		doPost(req, resp);
	}

	@Override
	protected void doPost(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		System.out.println("=====进入doPost方法=====");

		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);
		
		String forward=null;
		
		if(userName.equals("dc")&&password.equals("123")){
			//请求转发，使用请求转发不可以访问其他应用的地址
			/*forward="/14/success.jsp";
			//forward="http://www.jikexueyuan.com";
			RequestDispatcher rd = req.getRequestDispatcher(forward);
			rd.forward(req, resp);*/
			//请求重定向,使用请求重定向可以访问其他应用的地址
			forward="http://www.jikexueyuan.com";
			resp.sendRedirect(forward);
			//resp.sendRedirect(req.getContextPath()+"/14/success.jsp");
		}else{
			//请求转发
			forward="/14/error.jsp";
			RequestDispatcher rd = req.getRequestDispatcher(forward);
			rd.forward(req, resp);
			//请求重定向
			//resp.sendRedirect(req.getContextPath()+"/14/error.jsp");
		}
	}

}

```

{% codeblock lang:java This is Java %}
package com.whut.servlet;

import java.io.IOException;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class LoginServlet extends HttpServlet {

	/**
	 * 
	 */
	//用于序列化和反序列化
	private static final long serialVersionUID = 4426037562056379764L;

	/*@Override
	protected void service(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);
	}*/

	@Override
	protected void doGet(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		/*System.out.println("=====进入doGet方法=====");
		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);*/
		doPost(req, resp);
	}

	@Override
	protected void doPost(HttpServletRequest req, HttpServletResponse resp)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		System.out.println("=====进入doPost方法=====");

		String userName=req.getParameter("uname");
		String password=req.getParameter("upwd");
		
		System.out.println("用户名 ==》"+userName);
		System.out.println("密码==》"+password);
		
		String forward=null;
		
		if(userName.equals("dc")&&password.equals("123")){
			//请求转发，使用请求转发不可以访问其他应用的地址
			/*forward="/14/success.jsp";
			//forward="http://www.jikexueyuan.com";
			RequestDispatcher rd = req.getRequestDispatcher(forward);
			rd.forward(req, resp);*/
			//请求重定向,使用请求重定向可以访问其他应用的地址
			forward="http://www.jikexueyuan.com";
			resp.sendRedirect(forward);
			//resp.sendRedirect(req.getContextPath()+"/14/success.jsp");
		}else{
			//请求转发
			forward="/14/error.jsp";
			RequestDispatcher rd = req.getRequestDispatcher(forward);
			rd.forward(req, resp);
			//请求重定向
			//resp.sendRedirect(req.getContextPath()+"/14/error.jsp");
		}
	}

}


{% endcodeblock%}

