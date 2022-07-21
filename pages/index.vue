<template>
	<div>
		<div class="header">
			<div class="header_wrap">
				<div class="logo" @click="goToTop()">
					<i class="el-icon-top"></i>
				</div>
				<el-dropdown>
					<span class="el-dropdown-link">
						導覽列<i class="el-icon-arrow-down el-icon--right"></i>
					</span>
					<el-dropdown-menu slot="dropdown">
						<el-dropdown-item @click.native="scrollToPage(0)">Express 研究手冊</el-dropdown-item>
						<el-dropdown-item v-for="(page,index) in page_data" :key="index"
							@click.native="scrollToPage(page.num)">ch{{page.num - 1}} {{page.name}}</el-dropdown-item>
					</el-dropdown-menu>
				</el-dropdown>
			</div>
		</div>
		<div class="container">
			<div class="first_page">
				<!-- <logo /> -->
				<img class="img" src="../assets/image/logo.png" alt="image">
				<h2 class="subtitle">研究手冊</h2>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">前言</div>
				</div>
				<div class="content_wrap">
					<div>
						<p>Express 是一個簡潔而靈活的 node.js Web應用框架, 提供了一系列強大特性幫助你創建各種 Web 應用，和豐富的 HTTP 工具。</p>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">認識Express</div>
				</div>
				<div class="content_wrap">
					<div class="title">什麼是Express？</div>
					<div class="content">
						<p>他是一個簡潔而靈活的 node.js Web應用框架, 提供了一系列強大特性幫助你創建各種 Web 應用，和豐富的 HTTP 工具。</p>
						<p>他是建構在Node.js中介軟體模組的，我們叫它connect，它的運作就是在處理HTTP請求的函數；每處理完一個中介軟體函式，會再傳給下一個中間軟體的函式。</p>
					</div>
					<div class="title">優點</div>
					<div class="content">
						<ul>
							<li>快速，集思廣益，極簡的Node.js Web架構</li>
							<li>容易配置及客製化</li>
							<li>可以為你應用程式的Http methods及URLs 定義路由(Routes)</li>
							<li>包含不同的中介軟件，讓你可以在request及respones間，加入一些任務執行</li>
							<li>容易與不同的模板引擊整合，像是Jade, Vash, EJS…。</li>
							<li>允許你定義一個錯誤處理的中介軟件。</li>
							<li>容易為你的應用程式提供靜態文件和資源</li>
							<li>允許你建立 REST API server</li>
							<li>易於與database做連線，像是MongoDB, Redis, MySQL</li>
						</ul>
					</div>
					<div class="title">安裝</div>
					<div class="content">
						<p>這邊假設你已安裝node.js，請建立目錄來保留你的應用程式，並使它成為你的工作目錄</p>
						<pre><code>$ mkdir myapp</code><code>$ cd myapp</code></pre>
						<p>使用 npm init 指令，為您的應用程式建立 package.json 檔。</p>
						<pre><code>$ npm init</code></pre>
						<p>這個指令會提示您提供一些事項，例如：您應用程式的名稱和版本。現在，您只需按下 RETURN 鍵，接受大部分的預設值，但下列除外：</p>
						<pre><code>entry point: (index.js)</code></pre>
						<p>輸入 app.js，或您所要的主要檔名稱。如果您希望其名稱是 index.js，請按 RETURN 鍵，接受建議的預設檔名。</p>
						<p>現在，將 Express 安裝在 myapp 目錄中，並儲存在相依關係清單中。例如：</p>
						<pre><code>$ npm install express --save</code></pre>
						<p>如果只想暫時安裝 Express，而不新增至相依關係清單，請省略 --save 選項：</p>
						<pre><code>$ npm install express</code></pre>
						<p>PS：安裝 Node 模組時，如果指定了 --save 選項，則會將這些模組新增至 package.json 檔中的 dependencies 清單。之後，當您在 app 目錄中執行
							npm install 時，就會自動安裝相依關係清單中的模組。</p>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">入門</div>
				</div>
				<div class="content_wrap">
					<div class="title">Express應用程式產生器</div>
					<div class="content">
						<p>使用應用程式產生器工具 express，快速建立應用程式架構。</p>
						<p>使用下列指令來安裝 express：</p>
						<pre><code>$ npm install express-generator -g</code></pre>
						<p>使用 -h 選項來顯示指令選項：</p>
						<img class="img" src="../assets/image/page1.jpg" alt="image">
						<p>舉例來說，以下是在現行工作目錄中建立一個名為 myapp 的 Express 應用程式：</p>
						<img class="img" src="../assets/image/page2.jpg" alt="image">
						<p>然後安裝相依項目：</p>
						<pre><code>$ cd myapp</code><code>$ npm install</code></pre>
						<p>在 MacOS 或 Linux 中，使用下列指令來執行應用程式：</p>
						<pre><code>$ DEBUG=myapp:* npm start</code></pre>
						<p>在 Windows 中，使用下列指令：</p>
						<pre><code>> set DEBUG=myapp:* & npm start</code></pre>
						<p>然後在瀏覽器中載入 http://localhost:3000/，以存取應用程式。</p>
						<p>產生的應用程式具有如下的目錄結構：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note01" />
						<p>PS：使用產生器來建立應用程式結構，只是多種用來建立 Express 應用程式結構的其中一種方式。您有權使用這種結構，或是加以修改盡量符合您的需求。</p>
					</div>
					<div class="title">基本路由</div>
					<div class="content">
						<p>路由是指判斷應用程式如何回應用戶端對特定端點的要求，而這個特定端點是一個 URI（或路徑）與一個特定的 HTTP 要求方法（GET、POST 等）。</p>
						<p>每一個路由可以有一或多個處理程式函數，當路由相符時，就會執行這些函數。</p>
						<p>路由定義的結構如下：</p>
						<pre><code>app.METHOD(PATH, HANDLER)</code></pre>
						<p>其中：</p>
						<ul>
							<li>app 是 express 的實例。</li>
							<li>METHOD 是 HTTP 要求方法。</li>
							<li>PATH 是伺服器上的路徑。</li>
							<li>HANDLER 是當路由相符時要執行的函數。</li>
						</ul>
						<p>下列範例說明如何定義簡單的路由。</p>
						<p>首頁中以 Hello World! 回應。</p>
						<pre><code>app.get('/', function (req, res) {</code><code>  res.send('Hello World!');</code><code>});</code></pre>
						<p>對根路由 (/)（應用程式的首頁）發出 POST 要求時的回應：</p>
						<pre><code>app.post('/', function (req, res) {</code><code>  res.send('Got a POST request');</code><code>});</code></pre>
						<p>對 /user 路由發出 PUT 要求時的回應：</p>
						<pre><code>app.put('/user', function (req, res) {</code><code>  res.send('Got a PUT request at /user');</code><code>});</code></pre>
						<p>對 /user 路由發出 DELETE 要求時的回應：</p>
						<pre><code>app.delete('/user', function (req, res) {</code><code>  res.send('Got a DELETE request at /user');</code><code>});</code></pre>
					</div>
					<div class="title">在Express中提供靜態檔案</div>
					<div class="content">
						<p>如果要提供影像、CSS 檔案和 JavaScript 檔案等之類的靜態檔案，請使用 Express 中的 express.static 內建中介軟體函數。</p>
						<p>將含有靜態資產的目錄名稱傳遞給 express.static 中介軟體函數，就能直接開始提供檔案。舉例來說，使用下列程式碼在名稱是 public 的目錄中，提供影像、CSS 檔案和
							JavaScript 檔案：</p>
						<pre><code>app.use(express.static('public'));</code></pre>
						<p>如果要使用多個靜態資產目錄，請呼叫 express.static 中介軟體函數多次：</p>
						<pre><code>app.use(express.static('public'));</code><code>app.use(express.static('files'));</code></pre>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">路由(Route)</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>路由是指應用程式端點 (URI) 的定義，以及應用程式如何回應用戶端要求。</p>
						<p>下列程式碼範例說明相當基本的路由。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note02" />
					</div>
					<div class="title">路由方法</div>
					<div class="content">
						<p>路由方法衍生自其中一個 HTTP 方法，並且會附加到 express 類別的實例中。</p>
						<p>下列程式碼範例說明對應用程式根目錄提出 GET 和 POST 方法時所定義的路由。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note03" />
						<p>Express 支援下列的路由方法，這些方法對應至 HTTP 方法：get、 post、put、head、delete、options、
							trace、copy、lock、mkcol、move、purge、propfind、proppatch、unlock、report、mkactivity、checkout、merge、m-search、notify、subscribe、unsubscribe、patch、search，以及
							connect。</p>
						<p>app.all() 是一個特殊的路由方法，它不是衍生自任何 HTTP 方法。此方法用來在所有要求方法的路徑中載入中介軟體函數。</p>
						<p>在下列範例中，不論您使用的是 GET、POST、PUT、DELETE 或 http 模組中支援的其他任何 HTTP 要求方法，都會針對傳給 “/secret” 的要求執行處理程式。
						</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note04" />
					</div>
					<div class="title">路由路徑</div>
					<div class="content">
						<p>當路由路徑配上要求方法時，即定義了發出要求時的目標端點。路由路徑可以是字串、字串型樣或正規表示式。</p>
						<p>以下是以字串為基礎的部分路由路徑範例。</p>
						<p>此路由路徑將符合傳送給根路由 / 的要求。</p>
						<pre><code>app.get('/', function (req, res) {</code><code>  res.send('root');</code><code>});</code></pre>
						<p>此路由路徑將符合傳送給 /about 的要求。</p>
						<pre><code>app.get('/about', function (req, res) {</code><code>  res.send('about');</code><code>});</code></pre>
						<p>此路由路徑將符合傳送給 /random.text 的要求。</p>
						<pre><code>app.get('/random.text', function (req, res) {</code><code>  res.send('random.text');</code><code>});</code></pre>
						<p>以下是以字串型樣為基礎的部分路由路徑範例，這邊開始都是正規表示法的符號。</p>
						<p>此路由路徑將符合 acd 和 abcd。</p>
						<pre><code>app.get('/ab?cd', function(req, res) {</code><code>  res.send('ab?cd');</code><code>});</code></pre>
						<p>此路由路徑將符合 abcd、abbcd、abbbcd 等。</p>
						<pre><code>app.get('/ab+cd', function(req, res) {</code><code>  res.send('ab+cd');</code><code>});</code></pre>
						<p>此路由路徑將符合 abcd、abxcd、abRABDOMcd、ab123cd 等。</p>
						<pre><code>app.get('/ab*cd', function(req, res) {</code><code>  res.send('ab*cd');</code><code>});</code></pre>
						<p>此路由路徑將符合 /abe 和 /abcde。</p>
						<pre><code>app.get('/ab(cd)?e', function(req, res) {</code><code>  res.send('ab(cd)?e');</code><code>});</code></pre>
						<p>只要路由名稱中有 “a”，都與這個路由路徑相符。</p>
						<pre><code>app.get(/a/, function(req, res) {</code><code>  res.send('/a/');</code><code>});</code></pre>
						<p>此路由路徑將符合 butterfly 和 dragonfly，但不符合 butterflyman、dragonfly man 等。</p>
						<pre><code>app.get(/.*fly$/, function(req, res) {</code><code>  res.send('/.*fly$/');</code><code>});</code></pre>
					</div>
					<div class="title">路由處理程式</div>
					<div class="content">
						<p>您可以提供其行為類似中介軟體的多個回呼函數，以處理要求。唯一的例外情況是這些回呼可能會呼叫
							next('route')，來略過其餘的路由回呼。如果沒有理由繼續處理現行路由，您可以使用這項機制，在路由中強制施行前置條件，然後將控制權傳遞給後續的路由。</p>
						<p>路由處理程式的形式可以是一個函數、函數陣列，或上述兩種的組合，如下列範例所示。</p>
						<p>單一回呼函數可以處理路由。例如：</p>
						<pre><code>app.get('/example/a', function (req, res) {</code><code>  res.send('Hello from A!');</code><code>});</code></pre>
						<p>多個回呼函數可以處理路由（請確定您有指定 next 物件）。例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note05" />
						<p>回呼函數陣列可以處理路由。例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note06" />
						<p>獨立函數與函數陣列的組合可以處理路由。例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note07" />
					</div>
					<div class="title">回應方法</div>
					<div class="content">
						<p>在下表中，回應物件 (res) 中的方法可以傳送回應給用戶端，並終止要求/回應循環。如果路由處理程式都沒有呼叫這些方法，用戶端要求將會停擺。</p>
						<ul>
							<li>res.download() => 提示您提供要下載的檔案。</li>
							<li>res.end() => 結束回應程序。</li>
							<li>res.json() => 傳送 JSON 回應。</li>
							<li>res.jsonp() => 傳送 JSON 回應，並支援 JSONP。</li>
							<li>res.redirect() => 將要求重新導向。</li>
							<li>res.render() => 呈現視圖範本。</li>
							<li>res.send() => 傳送各種類型的回應。</li>
							<li>res.sendFile() => 以八位元組串流形式傳送檔案。</li>
							<li>res.sendStatus() => 設定回應狀態碼，並以回應內文形式傳送其字串表示法。</li>
						</ul>
					</div>
					<div class="title">app.route()</div>
					<div class="content">
						<p>您可以使用 app.route()，來為路由路徑建立可鏈接的路由處理程式。由於是在單一位置指定路徑，建立模組路由很有用，因為它可減少冗餘和打錯字的情況。</p>
						<p>下列範例顯示利用 app.route() 所定義的路由處理程式鏈。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note08" />
					</div>
					<div class="title">express.Router</div>
					<div class="content">
						<p>express.Router類別用來建立可裝載的模組路由處理程式。Router實例是一個完整的中介軟體與路由系統；因此，常被稱為「迷你應用程式」。</p>
						<p>下列範例是將路由器建立成模組、在其中載入中介軟體函數、定義一些路由，並且將路由器模組裝載在主要應用程式中的路徑。</p>
						<p>接下來我們在routes資料夾底下新增一個web.js檔案，用來處理route的</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note09" />
						<p>然後將路由器模組(也就是app.js)載入應用程式中：</p>
						<pre><code>var webRouter = require('./routes/web');</code><code>...</code><code>app.use('/', webRouter);</code></pre>
						<p>現在，應用程式就能夠處理發給 / 的要求，並且呼叫該路由特定的 timeLog 中介軟體函數。</p>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">中介軟體(Middleware)</div>
				</div>
				<div class="content_wrap">
					<div class="title">前言</div>
					<div class="content">
						<p>中介軟體函數是一些有權存取要求物件 (req)、回應物件 (res) 和應用程式要求/回應循環中之下一個中介軟體函數的函數。下一個中介軟體函數通常以名為 next 的變數表示。</p>
						<p>中介軟體函數可以執行下列作業：</p>
						<ul>
							<li>執行任何程式碼。</li>
							<li>對要求和回應物件進行變更。</li>
							<li>結束要求/回應循環。</li>
							<li>呼叫堆疊中的下一個中介軟體。</li>
						</ul>
						<p>如果現行中介軟體函數不會結束要求/回應循環，它必須呼叫 next()，以便將控制權傳遞給下一個中介軟體函數。否則，要求將會停擺。</p>
						<p>下列範例顯示中介軟體函數呼叫中的元素：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note10" />
						<ul>
							<li>範例中的<code>get</code>就是要套用中介軟體函數的 HTTP 方法。</li>
							<li>範例中的<code>'/'</code>就是要套用中介軟體函數的路徑（路由）。</li>
							<li>範例中的<code>function</code>就是中介軟體函數。</li>
							<li>範例中的<code>next</code>就是中介軟體函數的回呼引數，依慣例，稱為 "next"。</li>
							<li>範例中的<code>res</code>就是中介軟體函數的 HTTP response 引數，依慣例，稱為 "res"。</li>
							<li>範例中的<code>req</code>就是中介軟體函數的 HTTP request 引數，依慣例，稱為 "req"。</li>
						</ul>
						<p>若要載入中介軟體函數，請呼叫 app.use()，以指定中介軟體函數。舉例來說，下列程式碼會在根路徑 (/) 路由之前先載入 myLogger 中介軟體函數。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note11" />
					</div>
					<div class="title">開發</div>
					<div class="content">
						<p>以下的簡單範例顯示一個稱為 “myLogger” 的中介軟體函數。當透過這個函數將要求傳遞給應用程式時，此函數只會列印 “LOGGED”。中介軟體函數會指派給名為 myLogger
							的變數。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note12" />
						<p>若要載入中介軟體函數，請呼叫 app.use()，以指定中介軟體函數。舉例來說，下列程式碼會在根路徑 (/) 路由之前先載入 myLogger 中介軟體函數。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note13" />
						<p>每當應用程式收到要求時，它會將 “LOGGED” 訊息列印至終端機。而且中介軟體的載入順序很重要：先載入的中介軟體函數也會先執行。如果 myLogger
							是在根路徑路由之後才載入，要求永不會抵達該函數，應用程式也不會列印 “LOGGED”，因為根路徑的路由處理程式會終止要求/回應循環。</p>
						<p>中介軟體函數 myLogger 只會列印訊息，然後呼叫 next() 函數，將要求傳遞給堆疊中的下一個中介軟體函數。下一個範例是在要求物件中新增一個稱為 requestTime
							的內容。我們將這個中介軟體函數命名為 “requestTime”。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note14" />
						<p>現在，應用程式會使用 requestTime 中介軟體函數。此外，根路徑路由的回呼函數會使用中介軟體函數新增至 req（要求物件）的內容。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note15" />
						<p>當您對應用程式根位置發出要求時，應用程式現在會在瀏覽器中顯示該要求的時間戳記。</p>
					</div>
					<div class="title">應用程式層次的中介軟體</div>
					<div class="content">
						<p>使用 app.use() 和 app.METHOD() 函數，將應用程式層次的中介軟體連結至 app object 實例，其中 METHOD 是中介軟體函數要處理的 HTTP
							要求方法（例如 GET、PUT 或 POST），並採小寫。</p>
						<p>本例顯示沒有裝載路徑的中介軟體函數。每當應用程式收到要求時，就會執行此函數。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note16" />
						<p>本例顯示裝載在 /user/:id 路徑的中介軟體函數。會對 /user/:id 路徑上任何類型的 HTTP 要求，執行此函數。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note17" />
						<p>本例顯示路由和其處理程式函數（中介軟體系統）。此函數會處理指向 /user/:id 路徑的 GET 要求。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note18" />
						<p>下列範例顯示使用裝載路徑在裝載點載入一系列中介軟體函數。其中說明中介軟體子堆疊，這個子堆疊會針對指向 /user/:id 路徑之任何類型的 HTTP 要求，列印其要求資訊。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note19" />
						<p>路由處理程式可讓您為一個路徑定義多個路由。下列範例為指向 /user/:id 路徑的 GET
							要求，定義兩個路由。第二個路由不會造成任何問題，卻絕不會呼叫，因為第一個路由會結束要求/回應循環。</p>
						<p>本例顯示中介軟體子堆疊，它處理了指向 /user/:id 路徑的 GET 要求。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note20" />
						<p>如果要跳過路由器中介軟體堆疊中其餘的中介軟體函數，請呼叫 next('route')，將控制權傳遞給下一個路由。PS： next('route') 只適用於使用 app.METHOD()
							或 router.METHOD() 函數載入的中介軟體函數。</p>
						<p>本例顯示中介軟體子堆疊，它處理了指向 /user/:id 路徑的 GET 要求。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note21" />
					</div>
					<div class="title">路由器層次的中介軟體</div>
					<div class="content">
						<p>路由器層次的中介軟體的運作方式如同應用程式層次的中介軟體，不同之處在於它會連結至 express.Router() 實例。</p>
						<pre><code>var router = express.Router();</code></pre>
						<p>請利用 router.use() 和 router.METHOD() 函數來載入路由器層次的中介軟體。</p>
						<p>下列的程式碼範例是使用路由器層次的中介軟體，抄寫上述針對應用程式層次的中介軟體顯示的中介軟體系統：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note22" />
					</div>
					<div class="title">錯誤處理中介軟體</div>
					<div class="content">
						<p>錯誤處理中介軟體函數的定義方式，與其他中介軟體函數相同，差別在於引數是四個而非三個，具體來說，就是使用 (err, req, res, next)) 簽章：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note23" />
					</div>
					<div class="title">內建中介軟體</div>
					<div class="content">
						<p>從 4.x 版起，Express 不再相依於 Connect。除了 express.static，Express 先前隨附的所有中介軟體函數現在位於個別的模組中。</p>
						<code>express.static(root, [options])</code>
						<p>Express 唯一的內建中介軟體函數是 express.static。此函數以 server-static 為基礎，負責在 Express 應用程式中提供靜態資產。</p>
						<p>root => 引數指定提供靜態資產的根目錄。</p>
						<p>options => 選用物件可具有下列內容：</p>
						<ul>
							<li>dotfiles => 用來提供點檔案的選項。可能的值是 “allow”、”deny” 和 “ignore” => 類型為string，預設為“ignore”</li>
							<li>etag => 啟用或停用 etag 的產生 => 類型為boolean，預設為true</li>
							<li>extensions => 設定副檔名遞補。 => 類型為array，預設為[]</li>
							<li>index => 傳送目錄索引檔。設定 false，會停用目錄檢索。 => 類型為混合，預設為"index.html"</li>
							<li>lastModified => 將 Last-Modified 標頭設為作業系統上檔案的前次修改日期。可能的值是 true 或 false。 =>
								類型為boolean，預設為true</li>
							<li>maxAge => 設定 Cache-Control 標頭的 max-age 內容，以毫秒為單位或 ms 格式的字串 => 類型為number，預設為0</li>
							<li>redirect => 當路徑名稱是目錄時，重新導向至尾端 “/”。 => 類型為boolean，預設為true</li>
							<li>setHeaders => 用來設定 HTTP 標頭以提供檔案的函數。 => 類型為function，預設為空</li>
						</ul>
						<p>下列範例顯示如何使用 express.static 中介軟體函數，且其中詳細闡述了 options 物件：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note24" />
						<p>每一個應用程式可有多個靜態目錄：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note25" />
					</div>
					<div class="title">協力廠商中介軟體</div>
					<div class="content">
						<p>使用協力廠商中介軟體，在 Express 應用程式中新增功能。可以針對必要的功能安裝 Node.js 模組，然後在應用程式層次或路由器層次將它載入到您的應用程式中。</p>
						<p>下列範例說明如何安裝和載入用來剖析 Cookie 的中介軟體函數 cookie-parser。</p>
						<pre><code>$ npm install cookie-parser</code></pre>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note26" />
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">在 Express 中使用範本引擎</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>您必須先設定下列應用程式設定，Express 才能呈現範本檔：</p>
						<ul>
							<li>views：範本檔所在的目錄。例如：app.set('views', path.join(__dirname, 'views'));</li>
							<li>view engine：要使用的範本引擎。例如：app.set('view engine', 'ejs');</li>
						</ul>
						<p>然後安裝對應的範本引擎 npm 套件：</p>
						<pre><code>$ npm install ejs --save</code></pre>
						<p>設定視圖引擎之後，您不必指定引擎或將範本引擎模組載入到應用程式中；Express 會在內部載入模組，如以下所示（針對上述範例）。</p>
						<pre><code>app.set('view engine', 'ejs');</code></pre>
						<p>在 views 目錄中，建立一個名稱是 index.ejs 的 Ejs 範本檔，內含下列內容：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note27" />
						<p>然後建立路由，以呈現 index.ejs 檔。如果未設定 view engine 內容，您必須指定 view 檔的副檔名。否則，您可以省略它。</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note28" />
						<p>當您向首頁提出要求時，index.ejs 檔會呈現成 HTML。</p>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">錯誤處理</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>錯誤處理中介軟體函數的定義方式，與其他中介軟體函數相同，差別在於錯誤處理函數的引數是四個而非三個：(err, req, res, next)。例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note29" />
						<p>您是在定義其他 app.use() 和路由呼叫之後，最後才定義錯誤處理中介軟體；例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note30" />
						<p>中介軟體函數內的回應可以是任何您喜好的格式，如：HTML 錯誤頁面、簡式訊息或 JSON 字串。上面的例子就是導到錯誤頁。</p>
						<p>為了方便組織（和更高層次的架構），您可以定義數個錯誤處理中介軟體函數，就像您處理一般中介軟體函數一樣。舉例來說，如果您想為使用及沒有使用 XHR
							所建立的要求，各定義一個錯誤處理程式，您可以使用下列指令：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note31" />
						<p>在本例中，通用的 logErrors 可能將要求和錯誤資訊寫入至 stderr，例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note32" />
						<p>此外在本例中，clientErrorHandler 定義成如下；在此情況下，會將錯誤明確傳遞給下一個：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note33" />
						<p>“catch-all” errorHandler 函數的實作方式如下：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note34" />
						<p>不論您傳遞何者給 next() 函數（'route' 字串除外），Express
							都會將現行要求視為發生錯誤，且會跳過其餘任何的非錯誤處理路由和中介軟體函數。如果您想以某種方式來處理該錯誤，您必須按照下一節的說明來建立錯誤處理路由。</p>
						<p>如果您的路由處理程式有多個回呼函數，可以使用 route 參數來跳到下一個路由處理程式。例如：</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note35" />
						<p>在上例中，會跳過 getPaidContent 處理程式，但是會繼續執行 app 中 /a_route_behind_paywall 的其餘處理程式。</p>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">位於 Proxy 背後的 Express</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>當 Express 應用程式是在 Proxy 背後執行時，請使用 app.set()，將 trust proxy 應用程式變數設為下表列出的其中一值。</p>
						<ul>
							<li>boolean => 若為 true，會將用戶端的 IP 位址視為 X-Forwarded-* 標頭中的最左側項目。若為
								false，會將應用程式視為直接面對網際網路，且用戶端的 IP 位址衍生自 req.connection.remoteAddress。這是預設值。</li>
							<li>IP => 要信任的 IP 位址、子網路，或是 IP 位址與子網路陣列。
								<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note36" />
								若有指定，位址判定程序中會排除 IP 位址或子網路，且會將最接近應用程式伺服器的未授信 IP 位址判斷為用戶端的 IP 位址。
							</li>
							<li>number => 信任來自正面 Proxy 伺服器的第 n 個躍點就是用戶端。</li>
							<li>function => 自訂信任實作。只有在您清楚自己要做什麼時，才能使用此項。
								<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note37" />
							</li>
						</ul>
						<p>如果設定 false trust proxy 以外的值，會造成三項重要的變更：</p>
						<ul>
							<li>req.hostname 值會衍生自 X-Forwarded-Host 標頭中所設定的值，且該值可能由用戶端或 Proxy 所設定。</li>
							<li>反向 Proxy 可能設定 X-Forwarded-Proto，以告知應用程式它是 https 或 http 或甚至是無效的名稱。req.protocol 會反映此值。
							</li>
							<li>req.ip 和 req.ips 值中會移入 X-Forwarded-For 中的位址清單。</li>
						</ul>
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">資料庫整合</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>如果要在 Express 應用程式中新增連接資料庫的功能，只需在您的應用程式中載入資料庫的適當 Node.js 驅動程式即可。本文件簡要說明如何在您的 Express
							應用程式中新增和使用一些最常用的 Node.js 資料庫系統模組。</p>
					</div>
					<div class="title">Cassandra</div>
					<div class="content">
						<p>模組：cassandra-driver 安裝</p>
						<pre><code>$ npm install cassandra-driver</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note38" />
					</div>
					<div class="title">CouchDB</div>
					<div class="content">
						<p>模組：nano 安裝</p>
						<pre><code>$ npm install nano</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note39" />
					</div>
					<div class="title">LevelDB</div>
					<div class="content">
						<p>模組：levelup 安裝</p>
						<pre><code>$ npm install level levelup leveldown</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note40" />
					</div>
					<div class="title">MySQL</div>
					<div class="content">
						<p>模組：mysql 安裝</p>
						<pre><code>$ npm install mysql</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note41" />
					</div>
					<div class="title">MongoDB</div>
					<div class="content">
						<p>模組：mongodb 安裝</p>
						<pre><code>$ npm install mongodb</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note42" />
					</div>
					<div class="title">Neo4j</div>
					<div class="content">
						<p>模組：apoc 安裝</p>
						<pre><code>$ npm install apoc</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note43" />
					</div>
					<div class="title">PostgreSQL</div>
					<div class="content">
						<p>模組：pg-promise 安裝</p>
						<pre><code>$ npm install pg-promise</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note44" />
					</div>
					<div class="title">Redis</div>
					<div class="content">
						<p>模組：redis 安裝</p>
						<pre><code>$ npm install redis</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note45" />
					</div>
					<div class="title">SQLite</div>
					<div class="content">
						<p>模組：sqlite3 安裝</p>
						<pre><code>$ npm install sqlite3</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note46" />
					</div>
					<div class="title">ElasticSearch</div>
					<div class="content">
						<p>模組：elasticsearch 安裝</p>
						<pre><code>$ npm install elasticsearch</code></pre>
						<p>範例</p>
						<vue-embed-gist gist-id="4d5ce6398d73f39a81560380eaa64416" file="note47" />
					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">請求(req)和響應(res)</div>
				</div>
				<div class="content_wrap">
					<div class="content">
						<p>Express 應用使用回調函數的參數： request 和 response 對象來處理請求和響應的數據。</p>
						<pre><code>app.get('/', function (req, res) { ... })</code></pre>
					</div>
					<div class="title">Request對象</div>
					<div class="content">
						<p>request 對象表示 HTTP 請求，包含了請求查詢字符串，參數，內容，HTTP 頭部等屬性。常見屬性有：</p>
						<ul>
							<li>req.app：當callback為外部文件時，用req.app訪問express的實例</li>
							<li>req.baseUrl：獲取路由當前安裝的URL路徑</li>
							<li>req.body / req.cookies：獲得「請求主體」/ Cookies</li>
							<li>req.fresh / req.stale：判斷請求是否還「新鮮」</li>
							<li>req.hostname / req.ip：獲取主機名和IP地址</li>
							<li>req.originalUrl：獲取原始請求URL</li>
							<li>req.params：獲取路由的parameters</li>
							<li>req.path：獲取請求路徑</li>
							<li>req.protocol：獲取協議類型</li>
							<li>req.query：獲取URL的查詢參數串</li>
							<li>req.route：獲取當前匹配的路由</li>
							<li>req.subdomains：獲取子域名</li>
							<li>req.accepts()：檢查可接受的請求的文檔類型</li>
							<li>req.acceptsCharsets / req.acceptsEncodings / req.acceptsLanguages：返回指定字符集的第一個可接受字符編碼
							</li>
							<li>req.get()：獲取指定的HTTP請求頭</li>
							<li>req.is()：判斷請求頭Content-Type的MIME類型</li>
						</ul>
					</div>
					<div class="title">Response對象</div>
					<div class="content">
						<p>response 對象表示 HTTP 響應，即在接收到請求時向客戶端發送的 HTTP 響應數據。常見屬性有：</p>
						<ul>
							<li>res.app：同req.app一樣</li>
							<li>res.append()：追加指定HTTP頭</li>
							<li>res.set()在res.append()後將重置之前設置的頭</li>
							<li>res.cookie(name，value [，option])：設置Cookie</li>
							<li>opition: domain / expires / httpOnly / maxAge / path / secure / signed</li>
							<li>res.clearCookie()：清除Cookie</li>
							<li>res.download()：傳送指定路徑的文件</li>
							<li>res.get()：返回指定的HTTP頭</li>
							<li>res.json()：傳送JSON響應</li>
							<li>res.jsonp()：傳送JSONP響應</li>
							<li>res.location()：只設置響應的Location HTTP頭，不設置狀態碼或者close response</li>
							<li>res.redirect()：設置響應的Location HTTP頭，並且設置狀態碼302</li>
							<li>res.render(view,[locals],callback)：渲染一個view，同時向callback傳遞渲染後的字符串，如果在渲染過程中有錯誤發生next(err)將會被自動調用。
								callback將會被傳入一個可能發生的錯誤以及渲染後的頁面，這樣就不會自動輸出了。</li>
							<li>res.send()：傳送HTTP響應</li>
							<li>res.sendFile(path [，options] [，fn])：傳送指定路徑的文件 -會自動根據文件extension設定Content-Type</li>
							<li>res.set()：設置HTTP頭，傳入object可以一次設置多個頭</li>
							<li>res.status()：設置HTTP狀態碼</li>
							<li>res.type()：設置Content-Type的MIME類型</li>
						</ul>

					</div>
				</div>
			</div>
			<div class="page">
				<div class="ch_wrap">
					<div class="code"></div>
					<div class="name">JWT(JSON Web Token)</div>
				</div>
				<div class="content_wrap">
					<div class="title">token的驗證機制</div>
					<div class="content">
						<p>我們應該常常能看到大量使用 token 來處理驗證的服務，由於大部分的網站服務開始大量使用 API，於是 token 就成了處理驗證使用者最好的方式。</p>
						<p>我們的應用程式選擇使用 token 驗證機制有些非常重要的原因，最主要是因為：</p>
						<ol>
							<li>對於伺服器來說它具備 stateless(無狀態), scalable(擴展性)</li>
							<li>移動裝置也能一併使用</li>
							<li>可將驗證結果導向其他應用程式</li>
							<li>更安全</li>
						</ol>
					</div>
					<div class="title">如何運作？</div>
					<div class="content">
						<p>基於 token 的驗證機制屬於無狀態的方式，我們不並需要在伺服器儲存任何關於使用者的資料。這個概念本身就是為了處理上述的那些問題。</p>
						<p>少了 session 表示我們的程式在使用負載平衡擴展伺服器時就不用因為這些資料交換的問題而受到限制。</p>
						<p>雖然實作有很多種方式，不過大致上流程如下:</p>
						<ol>
							<li>使用者提供帳密發出驗證請求</li>
							<li>程式驗證憑證</li>
							<li>程式提供回傳一個簽署過的 token 給客戶端</li>
							<li>客戶端儲存 token ，後續請求都必須要一併包含這個 token</li>
							<li>伺服器驗證 token 然後才回傳資料</li>
						</ol>
						<p>每一道request都要包含token。這個token應該要被包含在HTTP-header中，也因此這種方式達成了stateless的特性。接著我們就可以將伺服器的存取限制設定為Access-Control-Allow-Origin:*。關於ACAO-header中設定為*同時表示這不允許請求提供憑證例如:HTTP憑證,客戶端的SSL憑證或cookie。
						</p>
						<p>一旦通過驗證我們就會擁有token，我們就可以透過這個token做出許多應用。我們可以基於token建立授權甚至是傳遞給第三方應用使用。透過安全性token我們就可以決定哪些行為可以放行。
						</p>
					</div>
					<div class="title">優點</div>
					<div class="content">
						<p>最大的好處就是擴展性和stateless。因為stateless的關係我們的程式隨時都可以導入負載平衡。如果我們使用session那麼當使用者登入之後要繼續後續的動作就必須要把資料送回同一台伺服器。然後就可能對伺服器造成壓力。一旦採用token那麼這些問題就不用再擔心了。
						</p>
					</div>
					<div class="title">安全性</div>
					<div class="content">
						<p>token不像cookie，它會在每一次request的時候都要帶一次，因為沒有被存放到cookie中也就沒有機會被其他客戶端的程式直接存取。甚至是您將token儲存在cookie中，cookie也只是一種儲存方式而不是實際驗證機制。
						</p>
						<p>token也會過期，所以使用者會被要求在登入一次，這協助我們提高安全性。這裡提到token-revocation的概念，讓我們可以指定某個token失效或者是一整組基於同一個授權的token。
						</p>
					</div>
					<div class="title">擴展性</div>
					<div class="content">
						<p>token也可以讓我們的程式共享權限。舉例來說我們透過連結到社群平台驗證登入像是Facebook或Twitter。又例如當我們在Buffer給予Twitter權限那麼我們就可以透過Buffer發文到Twitter上。使用token我們就可以提供特定權限或功能給第三方的應用程式。
						</p>
					</div>
					<div class="title">跨平台與網域</div>
					<div class="content">
						<p>稍早我們提到CORS，當我們需要增加其他的服務或程式我們就需要提供存取權限給該網域或程式。又比如我們有一個API只負責提供資料，這個時候我們或許就會使用CDN來處理CORS的問題。如果我們可以直接把伺服器的設定換成
						</p>
						<pre><code>Access-Control-Allow-Origin: *</code></pre>
						<p>我們的資料或服務就可以提供給任何網域或程式來使用，當然你會說有安全性的問題，不過別忘了我們現在有 token 協助我們去驗證使用者。</p>
					</div>
					<div class="title">JSON Web Token是什麼？</div>
					<div class="content">
						<p>JSON Web Tokens 又稱 JWT 發音是 jot 從名字不難看出資料是透過 JSON 傳遞的。這裡有關於 JWT 的規格草稿，不過它並不好讀。</p>
						<p>JWT 可以在不同的語言中使用包含 .NET, Python, NodeJS, Java, PHP, Ruby, Go, Haskell 等。所以基本上在各種情況下我們都能夠使用。
						</p>
						<p>JWT 不相依於其他東西是可以獨立使用的: 它會包含自己所有需要的資料，意味著 JWT 是可以會傳送關於自身的基本資料，一個 payload	通常指的是使用者的資訊以及一個signature 簽章。</p>
						<p>JWT 可以被輕易的傳送: 因為 JWT 自身就包含了必須的資料且不依賴其他東西，因此當我們要透過 API 驗證的時候它可以完美的透過 HTTP header 或者網址來傳遞。</p>
						<p>JWT大致上就是由三個字串透過<code>.</code>組合而成，如下：</p>
						<pre><code>aaaaaaaaaa.bbbbbbbbbbb.cccccccccccc</code></pre>
						<p>第一個字串是header：標頭資訊，第二個字串是payload：處理的內容實際資料，第三個字串是signature：簽章。
						</p>
					</div>
					<div class="title">Header</div>
					<div class="content">
						<p>header 包含兩個部分</p>
						<ul>
							<li>宣告型別是 JWT</li>
							<li>使用的演算法，在這個例子中是 HMAC SHA256</li>
						</ul>
						<pre><code>{</code><code>    "typ": "JWT",</code><code>    "alg": "HS256"</code><code>}</code></pre>
						<p>一旦將上面的資訊使用 base64encode 我們就會得到第一個部分的 token</p>
						<pre><code>eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9</code></pre>
					</div>
					<div class="title">Payload</div>
					<div class="content">
						<p>關於 payload 大體來說就是需要處理的實際資料內容，這個 payload 通常會是整個 JWT 中比較重要的資料又稱 JWT Claims 即紀錄這個JWT的主張或者說本次傳輸主要的目的，主張是比較抽象的描述但具體來說就是資料。我們將想要傳送的資料和一些附加的資訊放在這裡。Claims可以不只一個，為了不產生疑義後續我們將使用英文術語- JWT Claims。</p>
					</div>
					<div class="title">Registered Claims</div>
					<div class="conetent">
						<p>關於 Claims 即傳遞的資料並不是必須的，不過根據規範我們可以使用下面這些預先定義好的 Claims 名稱讓我們可以使用：</p>
						<ul>
							<li>iss: 發行者的 token</li>
							<li>sub: 主題的 token</li>
							<li>aud: 接受者(聽眾)的 token</li>
							<li>exp: 這可能是 Registered Claims 最常用的，定義數字格式的有效期限，重點是有效期限一定要大於現在的時間</li>
							<li>nbf: 生效時間，定義一個時間在這個時間之前 JWT 不能進行處理</li>
							<li>iat: 發行的時間，可以被用來判斷 JWT 已經發出了多久</li>
							<li>jti: JWT 唯一的識別值，可用來防止 JWT 被重複使用，尤其在一次性的 token 特別好用</li>
						</ul>
					</div>
					<div class="title">Signature</div>
					<div class="content">
						<p>第三個部分就是簽章，這個簽章由下面三個部分組成</p>
						<ul>
							<li>header</li>
							<li>payload</li>
							<li>secret</li>
						</ul>
						<p>看看範例程式碼便知是如何得到</p>
						<pre><code>var encodedString = base64UrlEncode(header) + '.' + base64UrlEncode(payload)</code><code>HMACSHA256(encodedString, 'secret')</code></pre>
						<p>secret 的部分由伺服器持有，也因此伺服器才有辦法驗證 token 和簽發</p>
						<pre><code>6srTK4rBbOqlWj7le2hrwFP-iayHblLdhgVFIYU3gVg</code></pre>
						<p>最終得到的 JWT 就如同一開始提到的由兩個 . 串接三個編碼</p>
						<pre><code>eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJhbmR5eW91LmdpdGh1Yi5pbyIsImV4cCI6MTQ2NTcwMDMyODA5MiwibmFtZSI6ImFuZHl5b3UiLCJhZG1pbiI6dHJ1ZX0.6srTK4rBbOqlWj7le2hrwFP-iayHblLdhgVFIYU3gVg</code></pre>
						<p>總結來說 JWT 可以跨平台跨語言，讓不同的裝置應用或服務之間溝通，同時這個 token 可以搭配 URL, POST 參數, 或者 HTTP 標頭來傳遞使用。</p>
						<p>透過 JWT 讓我們可以快速方便的賦予 API 驗證機制。</p>
					</div>
				</div>
			</div>
		</div>
		<div class="footer">
			<span class="f_content">Copyright © <span class="f_name">Toby</span> Reserved</span>
		</div>
	</div>
</template>

<script>
// import Logo from '~/components/Logo.vue'
import VueEmbedGist from "vue-embed-gist";
export default {
	// loading: false,
	scrollToTop: true,
	components: {
		VueEmbedGist
	},
	data() {
        return {
			page_data:[],
		}
	},
	created: function() {// 生命週期順位 1

	},
	mounted: function() {// 生命週期順位 2
		// 顯示loading以及移除
		this.$nextTick(() => {
			this.$nuxt.$loading.start()
			setTimeout(() => this.$nuxt.$loading.finish(), 500)
		})
		let self = this;
		var page_array = []
		$('.page').each(function(){
			var array = {};
			var id = 'page'+$(this).index();
			$(this).prop('id',id);
			var chapter = 'chapter ' + ($(this).index()-1);
			$(this).find('.code').text(chapter);
			array.num = $(this).index();
			array.name = $(this).find('.name').text();
			page_array.push(array)
		})
		self.page_data = page_array;
	},
	computed: {// 屬性變更才動作

	},
    methods: {
		// 移動到某章節
		scrollToPage:function(index){
			let self = this;
			if(index != 0){
				var id = '#page'+index;
				var pageScrollTop = $(id).offset().top;
				$('html').animate({ 'scrollTop': pageScrollTop - 60 }, 250);
			}else{
				self.goToTop();
			}

		},
		// 回到最上面
		goToTop:function(){
			$('html').animate({ 'scrollTop': 0 }, 250);
		}
	},
	watch: {// 時刻監聽動作

	}
}
</script>
