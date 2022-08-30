# TurkceKonusmaTanimlama

## Kullanılan Modeller
Facebook XLS-R  
DeepSpeech 

## Kullanılan Paragraf
Yalnızlık Psikolojisi - Dr. Recai Yahyaoğlu kitabından ilk paragraf

Her şey bir ihtiyaçtan doğar. Yapılan her iş, iyi yada kötü bir anlam taşır ve her anlam hayata bakışımızı etkiler.
İnsanlar bu farklı bakış açılarına göre kısmen yalnızdırlar. Çünkü etraflarında onlar gibi olaylara aynı şekilde bakan ve algılayan kimse yoktur.
Bu yüzden iyi yada kötü anlamlar çağrıştıran, doğru ya da yanlış değerlendirilebilen ve kimi zaman ihtiyaç haline gelen
yalnızlık duygusunun tanınması gerekir.

Paragraf ses dosyası: paragraf.mp3

## Facebook XLS-R
Wav2vec2-large-xlsr-532 modeli 53 dil için 16 kHz ses dosyaları ile eğitilmiş bir modeldir.
Bu modeli Mozilla tarafından oluşturulan Common Voice3 adlı, 96 dilde 15.234 saati doğrulanmış olmak üzere toplam 20.817 saat veri içeren dataset ile xlsr-large-53 modeli üzerinde ince ayar yaparak kullanmayı denedim. İnternette Common Voice 6.1-2020-12-11 
dataseti ile hazırlanmış bir model bulunmaktadır4. Bu modeli oluşturan not defterini kullanarak datasetin en son sürümü olan 10.0-2022-07-04 versiyonunu kullanarak yeni bir model eğittim5.
Bu üç modeli (common voice 6.1 ile ince ayar yapılmış  xlsr-large-53 ozcangundes6 ve patrickvonplaten/wav2vec2-large-xlsr-turkish-demo modelleri
 ,  common voice 10.0 ile ince ayar yapılmış) kıyaslayıp paragraf için çıktılarını kıyasladım. Bu çıktılarda kelime hata oranlarını gösterdim. Model not defteri modelinin adıdır. model_original patrickvonplaten/wav2vec2-large-xlsr-turkish-demo modeli olan temel aldığım not defterindeki modeldir. model_base ise huggingface sayfasındaki ozcangundes modelidir. Amacım base modeli ile facebook modelini almaktı fakat dile özgü modeller için processor sunulmamaktaymış. 

## Sonuçlar
### Tahmin edilen metinler

Paragraf:
her şey bir ihtiyaçtan doğar. yapılan her iş, iyi yada kötü bir anlam taşır ve her anlam hayata bakışımızı etkiler.
i̇nsanlar bu farklı bakış açılarına göre kısmen yalnızdırlar. çünkü etraflarında onlar gibi olaylara aynı şekilde bakan ve algılayan kimse yoktur.
bu yüzden iyi yada kötü anlamlar çağrıştıran, doğru ya da yanlış değerlendirilebilen ve kimi zaman ihtiyaç haline gelen
yalnızlık duygusunun tanınması gerekir.

Not defteri modeli tahmin:

Orijinal not defteri modeli tahmin:
her şey bir ihtiyaştanduvar yapılan her viş iyi yada kötü bir anlam taşır ve her andan hayatapa kşimise etkiler i̇nsanlar bu farklı bakış açılarını göre kısınan yalnızdırlar çüngi yetraflamdaonlar gibi olaylara aynı şekilde bakan ve algalarenkimse yoktur bu yüzden iyii yada kötü anlamlar çağrıştıran doğru ya da yallışleğerlemdiilebilen vekim zaman ihtiye çarını gelenhannızlık duygu sunu tanınması gerekir

Wav2Vec2 Türkçe modeli tahmin:
her şeyi bir ihti yaştanbuar yapılan her içş iyi yılda kötü bir anlam taşır ve her andan hayatı bak şimise etkiler i̇nsanlar bu farklı bakışaçılarını görü kısına yalnızdırlar çüng etraflad unlar gibi olayları aynı şekilde bakan ve algalayan kimse yokturbu yüzden iyi yada kötü anlımlar çağrıştıran doğruyada yanlış değerlendirlebilen ve kimi zaman ihtiye çarını gelenyannızlık duygusunu tanınması gerekir

Kelime hata oranları (ne kadar az o kadar iyi)

Not defteri modeli hata oranı:
1.0
Orijinal not defteri modeli hata oranı:
0.5254237288135594
Wav2Vec2 Türkçe modeli hata oranı:
0.5932203389830508

Autocorrect sonrası çıktılar
Konuşma tanımlama modellerinden daha iyi sonuç elde etmek için autocorrect ile birlikte kullanıldığını öğrendim.

Not defteri modeli tahmin:

Orijinal not defteri modeli tahmin:
her şey bir ihtiyaştanduvar yapılan her şiş iyi yada kötü bir anlam taşır ve her andan hayatapa kşimise etkiler i̇nsanlar bu farklı bakış açılarını göre kısınan yalnızdırlar çengi yetraflamdaonlar gibi olaylara aynı şekilde bakan ve algalarenkimse yoktur bu yüzden iyi yada kötü anlamlar çağrıştıran doğru ya da yallışleğerlemdiilebilen vakim zaman itiye çarını gelenhannızlık duygu sunu tanınması gerekir
Wav2Vec2 Türkçe modeli modeli tahmin:
her şeyi bir ipti yaştanbuar yapılan her içi iyi yılda kötü bir anlam taşır ve her andan hayatı bak şiimse etkiler i̇nsanlar bu farklı bakışasılarını görü kısına yalnızdırlar çünkü etrafla unlar gibi olayları aynı şekilde bakan ve algılayan kimse yokturbu yüzden iyi yada kötü anlımlar çağrıştıran doğrucada yanlış değerlendirilebilen ve kimi zaman intiye çarını gelenyannızlık duygusunu tanınması gerekir

Kelime hata oranları

Not defteri modeli hata oranı:
1.0
Orijinal not defteri modeli hata oranı:
0.5084745762711864
Wav2Vec2 Türkçe modeli hata oranı:
0.559322033898305

Eksikler
- Kendi geliştirdiğim modelde öğrenme gerçekleşmiyor. colabda ses dosyalarının çoğunluğunu göremiyor/okuyamıyor. Colab bir süredir sıklıkla kullandığım için daha küşük kapasitede cihaz atıyor. Çalıştırabildiğim kod kapasite yetersiz diyor.

DeepSpeech
Türkçe için bu eğitimi yapan tek bir çalışma bulabildim. RashadGarayev tarafından geliştirilmiş model github reposunu buldum ve o aşamaları takip ettim. Fakat bir sonuç üretemedi. Felemenkçe için yapılan bir not defteri buldum. Bu aşamaları türkçe dataseti için uyarladım.  Not defterindeki training kısmını çalıştırınca bu modül bulunmamaktadır hatası verdi. Mozillanın hazırlandığı dökümantasyondaki eğitim kısmı eksik/problemli. Paket uyumsuzluğu ve bulunamayan python scriptleri var. virtualenv colabda problem çıkardığı için tekrar deneyeceğim.  


Kaynakça  
[Wav2vec2-large-xlsr-53](https://huggingface.co/blog/fine-tune-wav2vec2-english)  
[Common voice](https://commonvoice.mozilla.org/tr/datasets)  
[Fine-Tune XLSR-Wav2Vec2 on Turkish ASR with 🤗 Transformers (Model geliştirmek için kullanılan not defteri)](https://colab.research.google.com/drive/1euneFBjmIZ6_cvjkBXYao2kx61ieiqG3?usp=sharing)  
[Tüm çalışmaları gösteren not defteri](https://colab.research.google.com/drive/15-gbrhrz_hyXBi1CHYWbWy7WQH0VgRlD?usp=sharing)  
[ozcangundes modeli](https://huggingface.co/ozcangundes/wav2vec2-large-xlsr-53-turkish)  
[Türkçe Deepspeech](https://github.com/RashadGarayev/TRSpeech-to-text)  
[Felemenkçe Not defteri](https://colab.research.google.com/github/acabunoc/Tutorial-train-dutch-model/blob/master/DeepSpeech_train_a_model%2C_CV_Dutch.ipynb)  
[Eğitim Dökümantasyonu](https://github.com/mozilla/DeepSpeech/blob/master/doc/TRAINING.rst#training-your-own-model)  
[AutoCorrect modülü](https://github.com/StarlangSoftware/TurkishSpellChecker-Py)
