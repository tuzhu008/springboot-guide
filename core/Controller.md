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

`@Controller` 只是定义了一个控制器类，而使用 `@RequestMapping` 注解的方法才是真正处理请求的处理器，这个接下来就会讲到。

