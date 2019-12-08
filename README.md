# 计G191 2019322176 静永鑫
# 实验目的
掌握字符串String及其方法的使用
掌握异常处理结构
# 实验内容与要求
##  内容：1、选课界面实现
          2、选课退课
          3、输入输出文件流实现选课信息录入

#  实验过程
### 
### 选课录入txt
```java
File f1= new File(".."+File.separator+"选课.txt"); 
	FileWriter out;//声明写入字符的类,用于字符数据的写入
	BufferedReader br;//声明读去字符的缓存类,用于字符的读取
	BufferedWriter bw ;//声明写的缓存,用于字符数据的缓存写入
	String temp; //声明取出的一行字符串,通过while循环存入缓存中
	StringBuffer sb ;//声明字符串缓存区,对取出的数据进行缓存
	@Override
	
  
  public void actionPerformed(ActionEvent a) {
		String name = j6.getText();
		String scourse =(String)j5.getSelectedItem();
		System.out.println(scourse);
		course=new Course("1", scourse, "综合楼","3",3);
		int course_id = j5.getSelectedIndex();
		String[] teacher_name = {"张老师","李老师","王老师"};
		teacher=new Teacher(1, teacher_name[course_id], "男",0, course);
		student=new Student(1,name, "男",course,teacher);	   
        j9.setText(" "+student);
    	    try {
      	    	out=new FileWriter(f1,true);
      	    	out.write("  "+student.getname()+"  "+student.getCourse()+"  "+student.getTeacher()+"\n");
      	    	out.flush();
      	    	out.close();
			} catch (IOException e) {
				System.out.println("文件传输错误");
			}
		
	}
  ```
  
  ### 选课退课
  ```java
  	@Override
			public void actionPerformed(ActionEvent e) {
				try {
					String namet=j6.getText();
				    String courset=j5.getToolTipText();
					j9.setText(namet+" 课程已退: " +courset);				
					sb = new StringBuffer(4096);
					temp = null;
					br = new BufferedReader(new FileReader(f1)); 
					while((temp = br.readLine())!= null){ 
					       if ((temp.indexOf(namet))==-1) {
					    	   sb.append(temp).append("\r\n");
						}       
					} 
					br.close(); 
					bw = new BufferedWriter((new FileWriter(f1))); 
					bw.write(sb.toString()); 
					bw.close();
				} catch (IOException e1) {
					System.out.println("文件传输错误");
				}
				
			}
		});
```
    
 ### 流程图
   ---
    
    ![images](https://github.com/Jingyongxin/Java/blob/master/1.png)
    
### 运行结果
    ---
  ![images](https://github.com/Jingyongxin/Java/blob/master/3.png)
  ![images](https://github.com/Jingyongxin/Java/blob/master/4.png)
  
### 实验感想
通过这次最终Java编程实验，在同学的帮助下基本了解掌握字符串String及其方法的使用和异常处理结构，和如何设计GUI窗体，进一步培养l我利用Java语言进行编程和调试程序的能力。而实验过程中出现的错误，也通过老师和同学的解决并逐渐完善了程序，锻炼了自己的编程能力，收获良多。
  
