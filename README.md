# tku springboot class學期作業-2023 1024 update
## 學期作業

此倉儲用於淡江大學 202301 學期的作業。我們將使用 Maven 來構建專案，並要求您提交程式碼，以及一份介紹作業內容的 Word 文件。

## 專題內容

專題內容的題目是自訂的，您可以與您的導師討論並確定。

## 第一堂

### 課程大綱

在第一堂課中，我們將學習以下內容：

- 使用 Maven
- 使用集成開發環境 (IDE)
- Spring Boot 專案的啟動方式
- 如何編寫 Controller

## 第二堂

### 課程大綱

在第二堂課中，我們將學習以下內容：

#### 套用 log4j2

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-log4j2</artifactId>
</dependency>  ```

#### 套用Thymeleaf模板 (套用th tag)
```xml
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>  ```

####套用i18n
```xml
    src/main/java/org/tku/web/config/I18nConfiguration.java ```

## 第三堂
### 課程大綱
- i18n多國語系實作
```xml
    @GetMapping("/index")
    public String index(@RequestParam(required = false) String locale,
                        HttpServletRequest request, HttpServletResponse response) {
        if(StringUtils.isNotBlank(locale)) {
            localeResolver.setLocale(request, response, new Locale(locale));
        }
        return "index";
    }  ```

- 套用Thymeleaf模板 (套用layout tag)
```xml
    <dependency>
        <groupId>nz.net.ultraq.thymeleaf</groupId>
        <artifactId>thymeleaf-layout-dialect</artifactId>
    </dependency> ```

layout.html
```xml
<html xmlns:th="http://www.thymeleaf.org" xmlns:layout="http://www.ultraq.net.nz/thymeleaf/layout" >
    <head>
        <meta charset="utf-8">
        <title>Title</title>
        <link rel="stylesheet" th:href="@{/css/bootstrap.min.css}">
        <script th:src="@{/js/bootstrap.min.js}" ></script>
    </head>
    <body>
        <th:block th:include="common/nav :: nav"></th:block>
        <div layout:fragment="content"></div>
        <th:block th:include="common/footer :: footer"></th:block>
    </body>
</html>  ```

nav.html
```xml
<html xmlns:th="http://www.thymeleaf.org">
    <body >
        <th:block th:fragment="nav">
          <nav class="navbar navbar-expand-lg bg-primary">
            <div class="container-fluid">
              <a class="navbar-brand text-white" href="#">TKU</a>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                  <li class="nav-item">
                    <a class="nav-link active text-white" aria-current="page" th:href="@{/index}" th:text="#{common.index}">Home</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link text-white" th:href="@{/web/app1}" th:text="#{common.app1}"></a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link text-white" th:href="@{/web/app2}" th:text="#{common.app2}"></a>
                  </li>
                </ul>
              </div>
            </div>
          </nav>
        </th:block>
    </body>
</html>  ```

## 第四堂
### 課程大綱
- 套用Spring Security，實作登入/登出功能
- pom.xml
```xml
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-security</artifactId>
    </dependency>  ```























