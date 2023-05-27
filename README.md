# JavaScript Tərcümə Reposu

## Mündəricat

1. [Təqdimat](#təqdimat)
2. [İstifadə](#istifadə)
3. [İştirak](#iştirak)
4. [Etimad](#etimad)
5. [new.target](#newtarget)
6. [Tərcümələr](#tərcümələr)

## Təqdimat

**JavaScript Tərcümə Reposu**na xoş gəlmisiniz! Bu repo JavaScript haqqında Medium məqalələrimin tərcümələri toplusu kimi xidmət edir. Burada siz müxtəlif dillərdə təqdim olunan JavaScript-in füsunkar dünyasına dair çoxlu bilik və fikirlər xəzinəsini tapacaqsınız.

## Repo haqqında

Bu repo JavaScript ilə bağlı fikirlərimi, dərsliklərimi və kəşflərimi paylaşdığım Medium-dan tərcümə edilmiş məqalələrimin toplusudur. Hər bir tərcümə məzmunu müxtəlif dillərə çatdırmaqla daha geniş auditoriyaya əlçatan etmək məqsədi daşıyır.

## İstifadə

Reponu tədqiq etməkdən və mövcud tərcümələrə baxmaqdan çəkinməyin. Xüsusi dillərdə məqalələr tapmaq üçün qovluqlar arasında gəzə bilərsiniz. Tərcümə edilmiş hər bir məqalə ayrıca fayl kimi saxlanılır ki, bu da asan əldə etmək və istinad etmək imkanı verir.

Bu repodan maksimum yararlanmaq üçün sadəcə olaraq üstünlük verdiyiniz dili seçin və məqalələrə daxil olun. İstər yeni başlayan, istərsə də təcrübəli tərtibatçı olmağınızdan asılı olmayaraq, JavaScript haqqında anlayışınızı genişləndirmək üçün çoxlu məlumat və anlayışlar tapacaqsınız.

## İştirak

Bu repoya töhfələr qəbul edilir! Əgər siz mənim məqalələrimdən birini başqa dilə tərcümə etməkdə maraqlısınızsa və ya mövcud tərcümələrdə təkmilləşdirmələr təklif etmək istəyirsinizsə, lütfən, bu addımları yerinə yetirin:

1. Bu reponu GitHub hesabınıza bağlayın.
2. Tərcümə və ya dəyişiklikləriniz üçün yeni branch yaradın.
3. Tərcümədə dəqiqliyi və aydınlığı təmin edərək, öz dəyişikliklərinizi edin.
4. Dəyişikliklərinizi yerinə yetirin və onları fork reponuza pushlayın.
5. Etdiyiniz dəyişiklikləri və tərcümə etdiyiniz dili izah edən pull request göndərin.

İştirakınız JavaScript biliklərini bütün dünyada insanlar üçün daha əlçatan etməyə kömək edəcək.

## Etimad

Məqalələrimi tərcümə etmək üçün vaxt və səylərini sərf edən bütün iştirakçılara təşəkkürümü bildirmək istəyirəm. Biliyin yayılmasında və dil maneələrinin aradan qaldırılmasında töhfələriniz əvəzsizdir.

## Əlaqə

Bu repozitoriya və ya tərcümələrlə bağlı hər hansı sualınız, təklifiniz və ya rəyiniz varsa, lütfən mənimlə əlaqə saxlayın. GitHub vasitəsilə mənimlə əlaqə saxlaya və ya əlaqə məlumatımı Medium profilimdə tapa bilərsiniz.

Tərcümə edilmiş JavaScript məqalələrimə maraq göstərdiyiniz üçün təşəkkür edirəm! Gəlin birlikdə dünya üzrə tərtibatçıları JavaScript səyahətlərində üstün olmaq üçün lazım olan biliklərlə gücləndirək.

Xoş kodlaşdırma və xoş tərcümələr!

## Newtarget

### Giriş:

JavaScript kəşf gözləyən gizli qiymətli daşlarla dolu möcüzələr və sirlər aləmidir. Belə incilərdən biri konstruktorların və onların törəmə siniflərinin sirlərini açmağa imkan verən xüsusi və sehrli xüsusiyyət olan “new.target” xüsusiyyətidir. Bu epik məqalədə biz sizi güldürəcək yumoristik və məzəli dəyişən adlarla new.target aləmində səyahətə çıxırıq.

### Sirli new.target xassəsi:

Gəlin sizi ilk qəhrəmanımız olan `new.target` ilə tanış edək. Bu, `new` açar sözü ilə çağırılan zaman konstruktor funksiyası və ya metodu daxilində avtomatik müəyyən edilən xüsusiyyətdir. Bu sehrli xüsusiyyət birbaşa çağırılan konstruktora və ya sinfə istinad edir və bizə nümunənin əsl mənşəyini anlamağa imkan verir.

### Böyük Konstruktor Axtarışı:

Təsəvvür edin ki, bizdə “Heyvanlar” kimi tanınan, hər biri özünəməxsus qabiliyyət və xüsusiyyətlərə malik fantastik canlılar diyarı var. Konstruktorlarımız olduqca məzəli bir şəkildə adlanır və nağılımıza maraq əlavə edir. Qəhrəmanlarımızla tanış olaq:

```js

class Animal {
  constructor() {
    if (new.target === Animal) {
      this.species = 'Mysterious';
      console.log('A new Animal has been created!');
    } else {
      console.log('A new Animal has been summoned from another dimension!');
    }
  }
}
```

Yuxarıdakı misalda biz `new Animal()` istifadə edərək nümunə yaratdıqda, konstruktor daxilindəki `new.target` xüsusiyyəti Animal konstruktorunun özünə istinad edəcək. Bununla belə, `new Dog()` kimi törəmə sinifdən istifadə edərək nümunə yaratsaq, `new.target` xassəsi bunun əvəzinə törəmə sinfi göstərəcək.

Möhtəşəm məxluqların törəməsi:
İndi isə sevimli Heyvanımızdan miras qalan Dog adlı törəmə sinfi təqdim edək:

```js

class Dog extends Animal {
  constructor() {
    super();
    console.log('A new Dog has entered the scene!');
  }
}
```

Biz `new Dog()` istifadə edərək yeni İt nümunəsini yaratdıqda konstruktor yerinə yetirilir. Nəticədə, həm Heyvan, həm də İt konstruktorları kaskad şəkildə çağırılır. `New.target` köməyi ilə biz Heyvan və İt nümunələrini fərqləndirə, onların yaradılmasının sirrini aça bilərik.

Qüdrətli Çağırıcı:
Amma gözləyin, daha çox var! new.target-in gücü konstruktorlardan kənara çıxır. O, həmçinin statik metodlar və qeyri-konstruktor funksiyaları daxilində istifadə oluna bilər:




```js

function summonAnimal() {
  if (new.target) {
    console.log('An Animal is being summoned!');
  } else {
    console.log('An Animal is appearing through unknown means!');
  }
}
```
Bu özünəməxsus funksiyada biz summonAnimal() funksiyasını birbaşa çağırdığımızda, `new.target` qeyri-müəyyən olacaq. Bununla belə, əgər biz new summonAnimal() funksiyasından istifadə etsək, new.target funksiyanın özünə istinad edəcək və onun konstruktor kimi çağırıldığını göstərir.

Nəticə:
Biz new.target səltənətində həyəcanverici macəraya başladıq, onun sehrli güclərini kəşf etdik və konstruktorların və törəmə siniflərin sirlərini açdıq. Məzəli və əyləncəli dəyişən adların toxunuşu ilə ümid edirik ki, bu səyahət üzünüzə təbəssüm gətirdi.

Bir tərtibatçı olaraq,unutmayın ki bu, təkcə mürəkkəblikləri aradan qaldırmaq deyil, həm də kodumuzda tapıla bilən məzəli və yumoru əhatə etməkdir. 

Xoş kodlaşdırmalar, macəraçılar!

**[⬆ əvvələ](#Mündəricat)**

## Tərcümələr

Bu digər dillərdə də mövcuddur:

- ![az](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Azerbaijan.png) **Azerbaijan**: [javidselimov/jsworldjs](https://github.com/javidselimov/jsworldjs)

**[⬆ əvvələ](#Mündəricat)**


