# Controller

Spring Boot 中使用 `@Controller` 注解标示一个类为控制器。

```java
@Controller
public class TestController {
    @RequestMapping("/test1")
    public ModelAndView test1() {
        ModelAndView mv = new ModelAndView();
        return mv;
    }
}
```

`@Controller` 只是定义了一个控制器类，而使用 `@RequestMapping` 注解的方法才是真正处理请求的处理器。

## `@RequestMapping` 标记的处理器方法支持的方法参数和返回类型

### 方法参数类型

* **HttpServlet 对象，主要包括 HttpServletRequest、HttpServletResponse 和 HttpSession 对象。**

* （1 ）HttpServlet 对象，主要包括HttpServletRequest 、HttpServletResponse 和HttpSession 对象。 

这些参数Spring 在调用处理器方法的时候会自动给它们赋值，所以当在处理器方法中需要使用到这些对象的时候，可以直接在方法上给定一个方法参数的申明，然后在方法体里面直接用就可以了。但是有一点需要注意的是在使用HttpSession 对象的时候，如果此时HttpSession 对象还没有建立起来的话就会有问题。



   （2 ）Spring 自己的WebRequest 对象。 使用该对象可以访问到存放在HttpServletRequest 和HttpSession 中的属性值。



   （3 ）InputStream 、OutputStream 、Reader 和Writer 。 InputStream 和Reader 是针对HttpServletRequest 而言的，可以从里面取数据；OutputStream 和Writer 是针对HttpServletResponse 而言的，可以往里面写数据。



   （4 ）使用@PathVariable 、@RequestParam 、@CookieValue 和@RequestHeader 标记的参数。



   （5 ）使用@ModelAttribute 标记的参数。



   （6 ）java.util.Map 、Spring 封装的Model 和ModelMap 。 这些都可以用来封装模型数据，用来给视图做展示。



   （7 ）实体类。 可以用来接收上传的参数。



   （8 ）Spring 封装的MultipartFile 。 用来接收上传文件的。



   （9 ）Spring 封装的Errors 和BindingResult 对象。 这两个对象参数必须紧接在需要验证的实体对象参数之后，它里面包含了实体对象的验证结果。

### 返回类型



