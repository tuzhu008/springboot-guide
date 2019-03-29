# Controller

Spring Boot 中使用 `@Controller` 注解标示一个类为处理器。

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



