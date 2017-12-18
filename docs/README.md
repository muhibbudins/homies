# Converting Design to HTML 

## Pendahuluan

> Sebelum memulai ada baiknya kalian mempersiapkan beberapa tools yang akan kita gunakan dan bisa kalian baca pada bagian [README.md](README.md)

Apa sih template? apa pernah menggunakan HTML template? bagaimana cara membuatnya? seperti apakah kesulitan membuatnya?

> Kadang pertanyaan seperti ini saya dapatkan dari beberapa teman yang bekerja web developer

Kadang kala, mereka membuat tampilan website dengan menggunakan template gratis / berbayar yang sudah tersedia di internet. Tapi suatu ketika mereka mendapatkan tugas untuk meng–kustom template tersebut sesuai kebutuhan dari si client atau bosnya.

Disini masalahnya terjadi, terkadang ada beberapa web developer membuat kustomisasi yang berakhir dengan rusaknya struktur dari template tersebut dan ujungnya tampilan dari templatenya lebih acak-acakan.

## Apa yang dibutuhkan?

Web Programmer sebetulnya terbagi menjadi beberapa bidang yang bisa di sebut spesialisasi dan teruntuk pembuat template ini biasa di sebut Web Designer yang sebetulnya bisa di bagi lagi menjadi spesialisasi lain seperti UI Designer, UX Designer, Interaction Designer, Template / Slicing Designer dsb.

Lalu untuk menjadi seorang Web Designer itu apa saja yang dibutuhkan?

1. Sense of art, *mengerti* dan tau apa yang disebut seni dan bisa membuat desain yang di sukai orang lain bukan oleh dirinya sendiri. *Mengerti* disini yaitu tau cara penggunaan dan penempatan font, color, layouting dll.

2. Dasar HTML, dengan memahami apa itu HTML dan cara menggunakannya kita dapat membuat struktur template yang teratur dan terlihat rapi.

3. Dasar CSS, lalu begitu pula dengan CSS *Cascading Style Sheet* dengan memahami CSS kita dapat membuat struktur style css terstruktur dan rapi. Selanjutnya setelah memahami dasar CSS kita di wajibkan memahami salah satu dari *Preprocessor CSS* yaitu SASS/SCSS, LESS, Stylus dan PostCSS untuk membantu kita dalam mempermudah pembuatan struktur dan style css.

Sebetulnya masih banyak yang menjadi sarat menjadi web designer yang sebetulnya berawal dari 3 poin di atas, tapi karena keterbatasan waktu kita bahas di lain kesempatan.

## Menyiapkan Aset Gambar

Beberapa hari yang lalu saya telah membuat desain landing page sebagai contoh untuk agensi desain rumah, bentuknya seperti ini :

![Desain](img/full.jpg)

Selanjutnya dalam pembuatan template ini saya telah melakukan slicing assets dari desain tersebut dan kalian bisa clone / download dari repository yang saya telah siapkan disini https://github.com/muhibbudins/homies atau bisa langsung clone dengan command `git clone git@github.com:muhibbudins/homies.git`

Pada folder homies saya telah membuat sebuah folder `img` yang berisi file-file assets yang dibutuhkan untuk membuat template ini.

## Mulai mendesain

Pada project ini kita akan menggunakan sebuah framework baru yang bernama **Spectre.css**, framework yang saya rasa masih banyak orang yang belum tahu dan cara penggunannya yang sangat simple. Kelebihan framework ini dibanding framework lain adalah sizenya yang sangat kecil (~10kb gzziped), desainnya yang elegan dan simple (mudah di custom), berbasis FlexBox, struktur penamaan class yang mengikuti standar BEM (metodologi BEM CSS) dan terakhir pengembangannya yang cukup cepat (rich experimental feature) info lebih lanjut silahkan kunjungi di reponya langsung https://picturepan2.github.io/spectre/

Lalu selanjutnya buka folder **homies** pada text editor / IDE kesukaan kalian dan silahkan buat file HTML bernama `index.html` pada folder **homies** lalu paste–kan code berikut :

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

	<title>Homies - Design Your Home</title>

	<!-- Meta Tag -->
	
	<!-- Style -->
	
	<!-- Icon & Fonts -->

</head>
<body>

	<!-- Our Code Will Be Here -->

</body>
</html>
```

Next, kita replace comment `<!-- Style -->` dengan code dibawah ini untuk memasukan **Spectre.css** kedalam project kita.

```html
	<!-- Include Spectre -->
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/spectre.css/0.5.0/spectre.min.css">
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/spectre.css/0.5.0/spectre-exp.min.css">

	<!-- Include Own Style -->
	<link rel="stylesheet" href="css/style.css">
```

Pada code diatas kita juga memasukan sebuah file `style.css` yang akan kita generate otomatis dari file SASS/SCSS

Lalu, replace comment `<!-- Icon & Fonts -->` dengan code dibawh ini untuk memasukan Google Fonts & IonIcons. By the way disini saya menggunakan 3 jenis font yaitu Lobster, Oswald (500) & Quicksand (400 & 500)

```html
	<!-- Include IonIcons -->
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/ionicons/2.0.1/css/ionicons.min.css">

	<!-- Include Google Fonts -->
	<link href="https://fonts.googleapis.com/css?family=Lobster|Oswald:500|Quicksand:400,500" rel="stylesheet">
```

Selanjutnya buatlah sebuah folder **scss** & **css** pada folder **homies**, jadi struktur foldernya saat ini adalah sebagai berikut :

```
- Homies
|- css
|- img
|- scss
|- .gitignore
|- index.html
|- LICENSE
|- README.md
```

Jika kalian mengikuti dengan seksama pendahuluan dan requirement pada bagian [Readme](README.md) seharusnya saat ini di komputer / laptop kalian sudah tersintal **Ruby SASS**. Bila belum terinstall silahkan buka dulu file [Readme](README.md) dan ikuti stepnya untuk menginstall **Ruby SASS**


Next, kita buat dahulu file `style.scss` pada folder **scss** selanjutnya jalankan command `sass --watch scss/style.scss:css/style.css` pada command prompt / terminal di folder **homies**. Jika berhasil seharusnya pada folder **css** ada 2 file baru bernama `style.css` & `style.css.map` serta sebuah folder baru di folder **homies** bernama `.sass-cache`.


Setelah itu buka file `style.scss` yang berada di folder **scss** dan paste-kan code di bawah ini sebagai variable yang akan kita butuhkan :

```scss
// Background
$bgHero      : url(../img/hero.png);
$bgTestimony : url(../img/testimony.png);
$bgProjects  : url(../img/projects.png);
$bgFooter    : url(../img/footer.png);

// Color
$background : #F7FAFF;
$green      : #2EC787;
$grass      : #43E09F;
$ocean      : #23CED9;
$blue       : #2EBEC7;
$darkblue   : #2D9CDB;

$darkBlack  : #252525;
$black      : #5C5C5C;
$darkGrey   : #717171;
$grey       : #828282;
$lightGrey  : #E0E0E0;

// Font
$quicksand : 'Quicksand', sans-serif;
$oswald    : 'Oswald', sans-serif;
$lobster   : 'Lobster', cursive;
```


Lalu, buka folder `index.html` dan kita siapkan struktur section yang terbagi menjadi 6 section yaitu Menu / Heading, Hero, Testimony, Project, Contact Us & Footer. Replace comment `<!-- Our Code Will Be Here -->` dengan code di bawah ini :

```html
	<!-- Heading -->
	<div class="heading">
	
	</div><!-- ./ Heading -->

	
	<!-- Hero -->
	<div class="hero">
	
	</div><!-- ./ Hero -->

	
	<!-- Testimony -->
	<div class="testimony">
	
	</div><!-- ./ Testimony -->

	
	<!-- Projects -->
	<div class="projects">
	
	</div><!-- ./ Projects  -->

	
	<!-- Contact Us -->
	<div class="contact-us">
    
    </div><!-- ./ Contact Us -->

	
	<!-- Footer -->
	<div class="footer">

	</div><!-- ./ Footer -->
```

> Ask something?

Setelah itu kita masukan code untuk heading / bagian menu, masukan code berikut setelah code `<div class"heading">`

```html
		<div class="container grid-lg">
			<div class="navbar">
				<div class="navbar-section">
					<a href="#" class="navbar-brand mr-2">Homies</a>
				</div>
				<div class="navbar-section">
					<a href="#" class="btn btn-link">Home</a>
					<a href="#" class="btn btn-link">Testimony</a>
					<a href="#" class="btn btn-link">Projects</a>
					<button class="btn btn-primary">Contact Us</button>
				</div>
			</div>
		</div>
```

> Jangan lupa buka browser kamu dan pastikan template ini menampilkan desain yang seharusnya (seperti pada desain)

Pada code di atas kita memiliki 1 brand name di sebelah kiri dan 4 menu di sebelah kanan, lalu kita custom style navbar di atas sesuai dengan desain yg di buat.

Pertama kita paste-kan code berikut di bawah code `$lobster   : 'Lobster', cursive;` pada folder **style.scss**, fungsinya untuk mengganti warna background browser dan menampilkan gambar tanaman diatas meja yang akan menjadi background pada bagian Hero nantinya.

```scss
/* Section Body */
body {
	background-color: $background;
	background-image: $bgHero;
	background-repeat: no-repeat;
	background-size: 700px 1000px;
	background-position: top right;
	font-family: $quicksand;
}
```

Dan kita paste-kan lagi code berikut di bawah code yang telah kita paste-kan tadi untuk memberikan efek bayangan pada navbar yg kita buat :

```scss
/* Section Heading */
.heading {
	background-color: white;
	box-shadow: 0px -4px 13px 0px rgba(20, 20, 20, 0.7);
}
```

Next, pada bagian navbar kita stylenya masih berbeda dengan yang ada pada desain maka dari itu kita paste-kan code berikut di bawah code bagaian `/* Section Heading */`

```scss
/* Sub Section Heading */
.navbar {
	padding: 15px 0;

	&-brand {
		color: $grass;
		font-family: $lobster;
		font-size: 28px;
		line-height: normal;
		margin-bottom: 5px;
	}
	.btn {
		color: lighten($darkGrey, 8%);
		padding: 6px 20px;
		font-size: 14px;

		&-active {
			color: $grass;
		}
		&-primary {
			background-color: $grass;
			border: 0;
			color: white;
			border-radius: 20px;
			margin-left: 20px;
		}
	}
}
```

Nice! navbarnya sudah lebih bagus sekarang, pada code diatas kita me–replace bagian `navbar-brand` dengan warna hijau dan mengganti jenis fontnya menjadi **Lobster** serta mengganti warna pada bagian menu sebelah kanan.

> Ask something?

Selanjutnya kita buat bagian Hero. Silahkan paste-kan code berikut pada bagian `<div class="hero">` dan refresh browser kalian :

```html
		<div class="hero-inner container grid-lg">
			<div class="hero-title">WE CAN DESIGN<br>YOUR FUTURE HOME</div>
			<div class="hero-sub_title">Maiores veritatis nisi quas iste vitae. Eius dolorem eos <br> autem, voluptates sint, quaerat nobis laboriosam neque.</div>
			<button class="btn btn-primary hero-btn">Learn More</button>
		</div>
```

Dan kita styling ulang bagian ini dengan paste-kan code berikut pada file `style.scss` di bawah bagian sub heading.

```scss
/* Section Hero */
.hero {
	width: 100%;
	min-height: calc(100vh - 70px);
	display: flex;
	align-items: center;
	justify-content: center;

	&-title {
		font-size: 64px;
		font-family: $oswald;
		color: $green;
		line-height: 1.1;
		margin-bottom: 10px;
	}
	&-sub_title {
		color: $darkGrey;
		margin-bottom: 40px;
		font-size: 16px;
	}
	.btn {
		border: 1px solid $darkblue;
		background-color: transparent;
		color: $darkblue;
		padding: 14px 48px;
		height: auto;
		border-radius: 30px;
	}
}
```

Pada code diatas kita membuat sebuah section bernama hero dengan tinggi 100vh (viewport height) dikurangi tinggi dari heading / menu (70px), lalu kita tambahkan property flex box untuk membuat content yg berada di dalamnya menjadi center vertical & horizontal. Serta mengganti warna dan ukuran title, sub title & button.


Next, bagian testimony. Di section ini kita akan membuat sebuah list dari review para customer yang sudah di desainkan rumahnya oleh agensi ini.

Paste-kan kode dibawah ini pada bagian `<div class="testimony">`:

```html
		<div class="testimony-inner container grid-lg">
			<div class="columns">
				<div class="column col-6">
					<div class="testimony-image">
						<img src="img/dummy/dummy-1.jpeg" alt="Table in the kitchen">
						<div class="testimony-avatar">
							<img src="img/dummy/user.jpeg" alt="">
						</div>
					</div>
				</div>
				<div class="column col-5 col-ml-auto">
					<div class="testimony-quote">
						<blockquote>
							<p>Voluptatibus voluptas, eaque eligendi consectetur quidem architecto at sit maxime aperiam provident molestiae itaque odit sunt. Maiores veritatis nisi quas iste vitae. Eius dolorem eos autem, voluptates sint, quaerat nobis laboriosam neque minus rerum nesciunt impedit laudantium!</p>
							<cite>~ Lucy Woon</cite>
						</blockquote>
					</div>
				</div>
			</div>
		</div>
```

Dan pada file `style.scss` kita paste-kan code berikut :

```scss
/* Section Testimony */
.testimony {
	width: 100%;
	min-height: 100vh;
	background-color: transparentize($blue, 0.35);
	background-image: $bgTestimony;
	background-repeat: no-repeat;
	background-size: contain;
	background-position: center left;
	display: flex;
	align-items: center;
	justify-content: center;
	position: relative;

	&:before {
		content: 'TESTIMONY';
		font-family: $oswald;
		letter-spacing: 20px;
		font-size: 164px;
		position: absolute;
		transform: translateX(60%) translatey(60%) rotate(-90deg);
		color: transparentize($black, 0.85);
	}
	&-image {
		width: 100%;
		border-radius: 20px;
		overflow: hidden;
		max-height: 300px;
		position: relative;
		box-shadow: 0 5px 14px 0px rgba(20, 20, 20, 0.3);

		&:before {
			content: '';
			position: absolute;
			top: 0;
			left: 0;
			bottom: 0;
			right: 0;
			background: transparent;  /* fallback for old browsers */
			background: -webkit-linear-gradient(to top, transparentize($darkBlack, 0.5), transparent);  /* Chrome 10-25, Safari 5.1-6 */
			background: linear-gradient(to top, transparentize($darkBlack, 0.5), transparent); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
		}
		img {
			width: 100%;
			height: 300px;
		}
	}
	&-avatar {
		position: absolute;
		width: 50px;
		height: 50px;
		border-radius: 50%;
		bottom: 25px;
		right: 25px;
		overflow: hidden;

		img {
			width: 100%;
			height: 100%;
		}
	}
	&-quote {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 300px;
		font-size: 14px;
		color: white;

		blockquote {
			border-left: 0;
		}
		cite {
			font-style: normal;
			font-weight: bold;
			font-size: 16px;
		}
	}
}
```

Pada code SCSS diatas kita mencustom bagian columns **Spectre.css** dengan menambahkan component seperti card untuk bagian image. Lalu di bagian dalam image tersebut ada bagian avatar untuk foto si customer juga menambahkan efek gradient sebagai overlay image. Mengganti background section dengan multiple background sekaligus yaitu warna biru transparan serta ornament image. Dan terakhir menambahkan ornament tulisan **TESTIMONY**	 pada bagian kanan section yang kita buat dengan pseuodo class `:before` di bagian `.testimony`.


Next, bagian yang cukup panjang dan memakan waktu lama untuk customnya :D yaitu bagian projects yang merubah langsung struktur grid dari **Spectre.css** menjadi masonry column seperti halnya Pinterest.

Silahkan pastkan code berikut pada bagian `<div class="projects">` untuk membuat button pada bagian atas section :

```html
		<div class="container grid-lg">
			<div class="columns">
				<div class="column col-mx-auto col-6 text-center">
					<button class="btn active">All</button>
					<button class="btn">Tables</button>
					<button class="btn">Chairs</button>
				</div>
			</div>

			<!-- Masonry Grid -->
		</div>
```

Dan paste-kan code berikut pada file `style.scss` :

```scss
/* Section Projects */
.projects {
	width: 100%;
	min-height: 1000px;
	background-image: $bgProjects;
	background-repeat: no-repeat;
	background-size: 800px 1850px;
	background-position: center left;
	position: relative;
	padding: 60px 0;

	&:before {
		content: 'PROJECTS';
		font-family: $oswald;
		letter-spacing: 20px;
		font-size: 164px;
		position: absolute;
		transform: translateX(10%);
		color: transparentize($black, 0.85);
		bottom: -4%;
	}
	.btn {
		border: 1px solid $grey;
		background-color: transparent;
		color: $grey;
		padding: 14px 32px;
		height: auto;
		border-radius: 30px;
		margin: 0 8px;

		&.active {
			border-color: $grass;
			color: $grass;
		}
	}

	// Masonry grid
}
```

Pada code diatas kita membuat sebuah bagian section projects dengan background image di belakang serta ornament tulisan **PROJECTS** pada bagian bawah section serta mengganti style dari button.

> Ask something?

Lalu, kita replace comment berikut `<!-- Masonry Grid -->` pada code sebelumnya dengan code di berikut yang berisi list project yg dimiliki oleh agensi rumah ini :

```html
			<!-- Projects Masonry  -->
			<div class="columns projects-masonry">
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Officia veniam alias numquam temporibus explicabo ducimus ullam consequuntur provident, perspiciatis, quibusdam nisi natus aliquam deleniti eveniet eius maxime sit iure odit!
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-2.jpeg" alt="Dummy 2">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Aperiam et sequi quibusdam modi fugit dignissimos expedita earum assumenda quis. Ipsa, consequuntur tempore animi molestiae sequi ratione iure iste et provident.
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-3.jpeg" alt="Dummy 3">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Debitis, consectetur, ex. Error officia repellendus porro minus hic excepturi assumenda enim, reprehenderit delectus soluta expedita, velit cupiditate accusantium fugit. Deserunt, obcaecati.
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-4.jpeg" alt="Dummy 4">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Non saepe, aliquam odio. Deserunt sapiente quidem quasi impedit asperiores labore ea dicta optio officiis, eligendi facere unde, at dignissimos vel recusandae.
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-5.png" alt="Dummy 5">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Nam id, ipsum quo. Enim, nemo, aliquam. Atque nesciunt blanditiis, iste illo, dolor nam praesentium molestias nisi ratione, totam ipsam facilis, eaque!
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-7.jpeg" alt="Dummy 7">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Sed qui laboriosam, molestiae architecto, asperiores iste deserunt vel officiis recusandae odio praesentium, beatae sit placeat neque ipsam nemo molestias assumenda unde!
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-1.jpeg" alt="Dummy 1">
					</div>
				</div>
				<div class="column col-4">
					<div class="projects-card">
						<div class="projects-overlay">
							<div class="projects-inner">
								<div class="projects-title">Some Title Here</div>
								<div class="projects-description">
									Minus corrupti neque aspernatur laboriosam ipsum quisquam inventore quas quo at expedita voluptatibus odio eaque quibusdam deserunt aliquid, illum reprehenderit mollitia itaque!
								</div>
								<div class="projects-btn">
									<a href="" class="btn">Detail</a>
								</div>
							</div>
						</div>
						<img src="img/dummy/dummy-6.jpeg" alt="Dummy 6">
					</div>
				</div>
			</div><!-- ./ Projects Masonry -->
```

Dan kita tambahkan style untuk mengcustom card diatas dengan code berikut (replace comment // Masonry grid pada file `style.scss`) :

```scss
	&-masonry {
	    flex-flow: column wrap;
	    max-height: 1200px;
	    margin-top: 40px;
	}
	&-card {
		width: 100%;
		height: auto;
		border-radius: 20px;
		overflow: hidden;
		margin-bottom: 20px;
		box-shadow: 0 5px 10px 0px rgba(20, 20, 20, 0.2);
		position: relative;
		min-height: 300px;

		img {
		    width: 100%;
		    height: 100%;
		    vertical-align: middle;
		    max-width: 100%;
		    transform-origin: 50% 0%;
		    transform: scale(1.6);
		    z-index: 0;
		}
		&:hover > .projects-overlay {
			opacity: 1;
		}
	}
	&-overlay {
		position: absolute;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		padding: 0 20px;
		background-color: transparentize($darkBlack, 0.4);
		color: white;
		opacity: 0;
		transition: all 0.3s ease-in-out;
		z-index: 10;
		cursor: default;

		.btn {
			padding: 12px 32px;
			font-size: 14px;
			color: white;
			border-color: white;
		}
	}
	&-title {
		font-size: 18px;
		font-weight: bold;
	}
	&-description {
		font-size: 14px;
		margin: 20px 0;
	}
```

Pada code diatas kita membuat list gambar dengan bentuk masonry grid, serta menambahkan overlay ketika gambarnya di hover untuk menampilkan title juga description dari gambar tersebut.

Section yang paling bawah adalah bagian Contact Us, kita paste-kan code di bawah ini pada bagian `<div class="contact-us">` :

```html
    	<div id="contact-us-map" class="contact-us-map"></div>
    	<div class="contact-us-text">
    		<div class="contact-us-inner">
    			<div class="contact-us-title">CONTACT US</div>
    			<div class="contact-us-description">
    				Distinctio illo, deleniti quam, dolores quis reprehenderit odit voluptate veniam ea harum consequuntur nobis ad, soluta tempora veritatis labore rerum dolore neque. Consectetur tenetur ratione quod asperiores ea.
    			</div>
    			<div class="contact-us-btn">
    				<a href="" class="btn">Detail</a>
    			</div>
    		</div>
    	</div>
```

Dan paste-kan code berikut pada file `style.scss` :

```scss
/* Section Contact */
.contact-us {
	width: 100%;
	min-height: 500px;
	position: relative;

	&-map {
	    position: relative;
	    width: 100%;
	    overflow: hidden;
	    height: 500px;
	    filter: grayscale(100%);
	    z-index: 0;
	}
	&-text {
		position: absolute;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
		background-color: transparentize($ocean, 0.35);
		background-image: $bgFooter;
		background-repeat: no-repeat;
		background-size: 100% 100%;
		background-position: center center;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	&-inner {
		width: 500px;
		text-align: center;
		color: white;
	}
	&-title {
		font-size: 32px;
		font-family: $oswald;
	}
	&-description {
		font-size: 14px;
		margin-top: 10px;
		margin-bottom: 40px;
	}
	.btn {
		padding: 8px 32px;
		font-size: 14px;
		color: white;
		border-color: white;
		background-color: transparent;
		height: auto;
		border-radius: 20px;
	}
}
```

Pada code diatas kita membuat section contact us dengan warna biru transparan serta ornamen di belakangnya. Dan pada bagian belakangnya kita akan menampilkan map dari Google Maps (bagian tambahan).

Bagian terakhir kita buat sebuah footer sebagai penutup template ini, paste-kan code berikut pada bagian `<div class="footer">` :

```html
		<div class="container grid-lg">
			<div class="navbar">
				<div class="navbar-section">
					<a href="#" class="navbar-brand mr-2">Copyright 2017 - Homies studio</a>
				</div>
				<div class="navbar-section">
					<a href="#" class="btn btn-link">
						<i class="ion-social-facebook"></i>
					</a>
					<a href="#" class="btn btn-link">
						<i class="ion-social-instagram"></i>
					</a>
					<a href="#" class="btn btn-link">
						<i class="ion-social-twitter"></i>
					</a>
				</div>
			</div>
		</div>
```

Dan paste-kan code berikut sebagai akhir dari file scss yg telah kita buat :

```scss
/* Section Footer */
.footer {
	width: 100%;
	padding: 20px;

	.navbar {
		&-brand {
			font-size: 14px;
			color: lighten($darkGrey, 2%);
			font-weight: normal;
		}
		.btn {
			color: lighten($darkGrey, 8%);
			font-size: 24px;
			padding: 6px 12px;
			color: $lightGrey;
		}
	}
}
```

Sekarang bisa di pastikan, templatenya sudah seperti desain yang telah di buat sebelumnya. Selanjutnya kita tinggal kembangkan lagi template ini menjadi lebih responsive karena pada dasarnya **Spectre.css** adalah framework yang saya rasa mengusung Adaptive desain bukan Responsive desain seperti pada framework kebanyakan.

## Bagian tambahan

Untuk bagian Testimony sebetulnya pada desain adalah sebuah slider, tapi karena keterbatasan waktu kita skip bagian ini dan bisa kalian kembangkan lebih lanjut.

Terakhir untuk menampilkan map silahkan buat API_KEY pada link berikut ... lalu paste-kan code berikut pada bagian atas tag `</body>` :

```html
	<!-- Include Google Maps API -->
	<script src="https://maps.googleapis.com/maps/api/js?key=API_KEY&callback=initMap" async defer></script>

	<!-- Load Maps to Wrapper -->
    <script type="text/javascript">
		function initMap() {
	        var map = new google.maps.Map(document.getElementById('contact-us-map'), {
				disableDefaultUI : true,
				center : { lat: -6.1753924, lng: 106.8271528 },
				zoom   : 15,
				styles : [{
				    featureType: "administrative",
				    elementType: "labels",
				    stylers: [{
				    	visibility: "off"
				    }]
				}, {
					featureType: "poi",
					elementType: "labels",
					stylers: [{
						visibility: "off"
					}]
				}, {
					featureType: "water",
					elementType: "labels",
					stylers: [{
						visibility: "off"
					}]
				}, {
					featureType: "road",
					elementType: "labels",
					stylers: [{
						visibility: "off"
					}]
				}]
	        });
		}
    </script>
```

### The End