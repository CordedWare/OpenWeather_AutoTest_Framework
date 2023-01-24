<h1>Java | Selenium | TestNG | Maven | POM | Rest Assured проект автотестов</h1>
<p>Это пример проекта на Java 11 Open JDK | Selenium WebDriver | TestNG | REST Assured | Maven созданный в IntelliJ IDE, с использованием модели Page Object Model и Generic Type.</p>
<p>Веб-сайт <a href="https://openweathermap.org/">https://openweathermap.org/</a>&nbsp;использовался для создания функциональных тестов, API тестов, и UI тестов.</p>
<p><a href="https://github.com/CordedWare/OpenWeather_AutoTest_Framework/blob/main/.github/workflows/ci.yml">ci.yml</a> файл использовался для рабочего процесса GitHub. <br /><br /><a href="https://github.com/dorny/test-reporter">dorny/test-reporter@v1</a> использовался для создания отчетов после каждого запуска CI.<br /><br /></p>
<p><strong>Используемые pom.xml dependencies:</strong></p>
<blockquote>
<pre>&lt;dependencies&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;org.testng&lt;/groupId&gt;<br />        &lt;artifactId&gt;testng&lt;/artifactId&gt;<br />        &lt;version&gt;7.6.1&lt;/version&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;org.seleniumhq.selenium&lt;/groupId&gt;<br />        &lt;artifactId&gt;selenium-java&lt;/artifactId&gt;<br />        &lt;version&gt;4.5.3&lt;/version&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;io.github.bonigarcia&lt;/groupId&gt;<br />        &lt;artifactId&gt;webdrivermanager&lt;/artifactId&gt;<br />        &lt;version&gt;5.3.0&lt;/version&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;com.google.code.gson&lt;/groupId&gt;<br />        &lt;artifactId&gt;gson&lt;/artifactId&gt;<br />        &lt;version&gt;2.10&lt;/version&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;com.fasterxml.jackson.core&lt;/groupId&gt;<br />        &lt;artifactId&gt;jackson-databind&lt;/artifactId&gt;<br />        &lt;version&gt;2.14.1&lt;/version&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;io.rest-assured&lt;/groupId&gt;<br />        &lt;artifactId&gt;rest-assured&lt;/artifactId&gt;<br />        &lt;version&gt;5.3.0&lt;/version&gt;<br />        &lt;scope&gt;test&lt;/scope&gt;<br />    &lt;/dependency&gt;<br /><br />    &lt;dependency&gt;<br />        &lt;groupId&gt;org.json&lt;/groupId&gt;<br />        &lt;artifactId&gt;json&lt;/artifactId&gt;<br />        &lt;version&gt;20220924&lt;/version&gt;<br />        &lt;scope&gt;test&lt;/scope&gt;<br />    &lt;/dependency&gt;<br /><br />&lt;/dependencies&gt;</pre>
</blockquote>
<h1>Тестирование API</h1>
<p>Для тестирования requests и responses использовался&nbsp;<strong>DevTools:&nbsp;</strong>&nbsp</p>
<blockquote>
<pre>&nbsp; DevTools devTools;<br /><br /></pre>
</blockquote>
<p>В классе CaptureNetworkTraffic был создан метод <strong>setUpDevTool(WebDriver driver)&nbsp;</strong> для перехвата трафика:</p>
<blockquote>
<pre><br />public&nbsp;CaptureNetworkTraffic setUpDevTool(WebDriver driver) {<br />&nbsp; &nbsp; &nbsp;devTools&nbsp;= ((ChromeDriver) driver).getDevTools();<br />&nbsp; &nbsp; &nbsp;devTools.createSession();<br />&nbsp; &nbsp; &nbsp;devTools.send(Network.enable(Optional.empty(), Optional.empty(), Optional.empty()));<br />&nbsp;<br />&nbsp; &nbsp; &nbsp;return this;<br />&nbsp;}&nbsp;</pre>
</blockquote>
<p><strong>org.openqa.selenium.devtools.v106.network.Network</strong>&nbsp;использовался для перехвата трафика.</p>
<p>Класс&nbsp;<strong>HttpURLConnection</strong>&nbsp;использовался для отправки прямых вызовов API и проверки ответов.<br /><br />Библиотека <strong>REST Assured</strong> и&nbsp;<strong>POJO Model</strong> использовались для тестирования и проверки REST API.</p>
<h1>Настройте проект и выполните тесты локально.</h1>
<p>1. Установите IntelliJ IDE:<br /><a href="https://www.jetbrains.com/help/idea/installation-guide.html">https://www.jetbrains.com/help/idea/installation-guide.html</a></p>
<p>2. Скопируйте HTTPS ссылку на проект из репозитория GitHub:&nbsp;<br /><a href="https://github.com/CordedWare/OpenWeather_AutoTest_Framework.git">https://github.com/CordedWare/OpenWeather_AutoTest_Framework.git</a></p>
<p>3. Клонируйте репозиторий из главного меню:&nbsp;<br /><a title="https://www.jetbrains.com/help/idea/cloning-repository.html#clone_project_from_main_screen" href="https://www.jetbrains.com/help/idea/cloning-repository.html#clone_project_from_main_screen">https://www.jetbrains.com/help/idea/cloning-repository.html#clone_project_from_main_screen</a></p>
<p>4. Перейдите к пакету "resources" package и скопируйте файл 'local.properties.TEMPLATE'. Вставьте его в пакет "resources" package и переименуйте новый файл как 'local.properties'.&nbsp;</p>
<p>5. Выполните тестовый класс или отдельный тест, открыв тестовый класс, щелкнув правой кнопкой мыши зеленый треугольник и выбрав «Run».</p>

