## 🟢 Ön bilgi

Bu rehberde Aleo ile sözleşme etkileşimine girmeyi anlatacağım 


 ### Linkler
 * [Hercules Telegram](https://t.me/HerculesNode)
 * [Hercules Twitter](https://twitter.com/HerculesNode)
   


## 🟢 Sistem Güncelleme
```shell
#!/bin/bash
sudo apt update && sudo apt upgrade -y
sudo apt-get install git-all -y
sudo apt-get install curl -y
sudo su
```

#### Cargo kuralım : 

```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
```shell
source "$HOME/.cargo/env"
```

## 🟢 Leo Dosyalarını çekelim

```shell
git clone https://github.com/AleoHQ/leo
```
```shell
cd leo
```
```shell
cargo install --path .
```

```shell
cd ..
```

## 🟢  üstteki güncellemeleri yaptıysanız buradan başlayalım

#### 1- Klasör oluşturalım

```shell
mkdir aleo_sozlesme_herculesnode && cd aleo_sozlesme_herculesnode
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/16243d42-a49d-46b3-8519-d0902521f5b4)


#### 2- Cüzdan adresi girelim 

```shell
WALLETADDRESS=CÜZDANINIZIN-ADRESİ
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/6828fcf1-901c-4b62-bbe0-ca5bf027e8d2)


#### 3- Program ismi oluşturacağız burası önemli  hercules yazan yeri kendi istediğiniz bir isimle değiştirin !  Burası değişecek = hercules

```shell
APPNAME=hercules_${WALLETADDRESS:4:6}
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/f1fe615e-4faa-4173-aa3f-f8c5ae620398)


#### 4- Leo test uygulaması oluşturalım  Buradaki çıktıyı not alalım kendi program ismimizi oluşturduk aşağıda kullanacağız önemli

```shell
leo new ${APPNAME}
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/1837eae4-2ed5-4cc0-9644-651931b345bf)


#### 5- Leo uygulamasını başlatalım

```shell
cd ${APPNAME} && leo run && cd -
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/54aa2013-7327-48f5-8495-e4a89b4695ab)


#### 6- Yolu kaydedelim

```shell
PATHTOAPP=$(realpath -q $APPNAME)
```

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/24179275-b6e7-4b52-926a-5d5068a549e2)


<hr> 

## 🟢 Şimdi buraya kadar işlemleri bitirdik artık aleo SDK üzerinden devam edeceğiz. 

#### 1- Bu adrese Gidelim :  https://aleo.tools/develop

<br> 

Alt tarafta bulunan Deploy Program bölümüne gelelim

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/e2253c47-67b8-4ce4-8f62-28b064491ec5)


#### 2- Program Bölümüne bunları yazalım  burada değiştireceğiniz alan Yukarıda 4. adımda oluşturduğumuz ismi yazacağız Not alın dediğim yeri 

```shell
program hercules_14mwla.aleo;

function hello:
input r0 as u32.public;
input r1 as u32.private;
add r0 r1 into r2;
output r2 as u32.private;
```
![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/c26e10b1-62be-468e-b9e1-b618051c605d)



#### 3- Private Key alanına Leo cüzdan private keyinizi yazın
#### 4- Estimate Fee butonuna basın güncel fee oranını otamatik yazacak tahmini 1.811 olacak
#### 5- Private Fee butonunu deaktif edin

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/b904dfb4-385a-4558-9343-e26fa671e5dc)




#### 6- Fee geldikten sonra Deploy tuşuna basın ve aşağıdaki gibi bir Onay alacaksınız 

![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/24d3c6c6-a478-4df1-92b2-e4b5ce6d5ecf)


#### 7- tx id kopyalayın buradaki adresin sonuna ekleyin ve kontrol edin https://explorer.aleo.org/transaction/


![image](https://github.com/HerculesNode/Aleo-Contract-Deploy/assets/101635385/b3436409-3cca-4061-bbaf-7fe542c87317)


#### işlemler bu kadar takıldığınız yerde telegram kanalıma gelebilirsiniz.


