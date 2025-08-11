# メモ

## 初期設定

```shell
docker compose up --detach

docker compose exec web bin/rails db:create
```

## scaffoldを使ってみる

```shell
docker compose exec web rails g scaffold Post title:string body:text

docker compose exec web rails db:migrate
```

## メールを送信してみる

### 設定

```shell
docker compose exec web rails g mailer User welcome_email
```

### コンソールで確認

```shell
$ docker compose exec web rails c

Loading development environment (Rails 8.0.2)
blog(dev)>
```

```shell
$ UserMailer.welcome_email.deliver_now

  Rendering layout layouts/mailer.html.erb
  Rendering user_mailer/welcome_email.html.erb within layouts/mailer
  Rendered user_mailer/welcome_email.html.erb within layouts/mailer (Duration: 0.2ms | GC: 0.0ms)
  Rendered layout layouts/mailer.html.erb (Duration: 2.6ms | GC: 0.0ms)
  Rendering layout layouts/mailer.text.erb
  Rendering user_mailer/welcome_email.text.erb within layouts/mailer
  Rendered user_mailer/welcome_email.text.erb within layouts/mailer (Duration: 0.2ms | GC: 0.0ms)
  Rendered layout layouts/mailer.text.erb (Duration: 0.5ms | GC: 0.0ms)
UserMailer#welcome_email: processed outbound mail in 5.3ms
Delivered mail 68997ae21da0b_ef004282c@15b3d15fb2e7.mail (260.5ms)
Date: Mon, 11 Aug 2025 05:08:50 +0000
From: from@example.com
To: to@example.org
Message-ID: <68997ae21da0b_ef004282c@15b3d15fb2e7.mail>
Subject: Welcome email
Mime-Version: 1.0
Content-Type: multipart/alternative;
 boundary="--==_mimepart_68997ae21a534_ef0042734";
 charset=UTF-8
Content-Transfer-Encoding: 7bit


----==_mimepart_68997ae21a534_ef0042734
Content-Type: text/plain;
 charset=UTF-8
Content-Transfer-Encoding: quoted-printable

User#welcome_email

=E3=81=93=E3=82=93=E3=81=AB=E3=81=A1=E3=81=AF, find me in app/views/user_=
mailer/welcome_email.text.erb


----==_mimepart_68997ae21a534_ef0042734
Content-Type: text/html;
 charset=UTF-8
Content-Transfer-Encoding: quoted-printable

<!-- BEGIN app/views/layouts/mailer.html.erb --><!DOCTYPE html>
<html>
  <head>
    <meta http-equiv=3D"Content-Type" content=3D"text/html; charset=3Dutf=
-8">
    <style>
      /* Email styles need to be inline */
    </style>
  </head>

  <body>
    <!-- BEGIN app/views/user_mailer/welcome_email.html.erb --><h1>User#w=
elcome_email</h1>

<p>
  =E3=81=93=E3=82=93=E3=81=AB=E3=81=A1=E3=81=AF, find me in app/views/use=
r_mailer/welcome_email.html.erb
</p>
<!-- END app/views/user_mailer/welcome_email.html.erb -->
  </body>
</html>
<!-- END app/views/layouts/mailer.html.erb -->=

----==_mimepart_68997ae21a534_ef0042734--

=> #<Mail::Message:126560, Multipart: true, Headers: <Date: Mon, 11 Aug 2025 05:08:50 +0000>, <From: from@example.com>, <To: to@example.org>, <Message-ID: <68997ae21da0b_ef004282c@15b3d15fb2e7.mail>>, <Subject: Welcome email>, <Mime-Version: 1.0>, <Content-Type: multipart/alternative; charset=UTF-8; boundary="--==_mimepart_68997ae21a534_ef0042734">, <Content-Transfer-Encoding: 7bit>>
```

### MailCatcherで確認

`http://localhost:1080/` にアクセス

## ブレイクポイント設定

```shell
docker compose attach web
```
