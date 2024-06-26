- [Unit Test Nedir?](#unit-test-nedir)
- [Unit Test Frameworks](#unit-test-frameworks)
- [xUnit ile Test Yazma Ornegi](#xUnit-ile-test-yazma-ornegi)
## Unit Test Nedir?
Unit test, yazılım geliştirme sürecinde birimin (genellikle bir fonksiyon veya metod) doğru çalışıp çalışmadığını kontrol etmek için yapılan otomatik testlerdir. Bu testler genellikle kodun her parçasının beklenen sonuçları üretip üretmediğini doğrulamak için kullanılır. Birim testleri, kodun düzeltilmesi gereken hataları erken aşamada tespit etmeye ve kodun kalitesini artırmaya yardımcı olur.

Birim testleri, yazılım geliştirme sürecinin başında ve süresince yazılımın doğru çalıştığından emin olmak için kullanılır. Her bir birim testi, belirli bir işlevi test eder ve bu işlevin beklenen girişlere ve çıkışlara uygun şekilde davranıp davranmadığını kontrol eder. Bu testler, yazılımın daha büyük bir sistem içindeki etkileşimlerini değil, yalnızca belirli birimlerin davranışlarını test ederler.

***

## Unit Test Frameworks 

C# dilinde yazılım geliştirme projelerinde kullanabileceğiniz birkaç birim test çerçevesi bulunmaktadır. İşte bunlardan bazıları:

## 1. NUnit

[NUnit](https://nunit.org/), C# ve .NET platformunda popüler bir birim test çerçevesidir. NUnit, çeşitli test durumlarını destekler, parametreli testler yapmanıza ve testleri düzenlemenize olanak tanır. NUnit, NUnit 2.x ve NUnit 3.x sürümleri arasında önemli farklılıklar bulunmaktadır.

## 2. xUnit.net

[xUnit.net](https://xunit.net/), C# ve .NET için modern bir birim test çerçevesidir. Basit ve temiz bir yapıya sahiptir ve özellikle .NET Core ve .NET 5 gibi yeni .NET platformlarında popülerdir. xUnit.net, testlerin paralel çalışmasını kolaylaştırır ve genellikle NUnit ve MSTest ile karşılaştırıldığında daha hızlıdır.

## 3. MSTest

Microsoft'un kendi birim test çerçevesi olan [MSTest](https://docs.microsoft.com/en-us/dotnet/core/testing/?view=netcore-3.1), Visual Studio ile birlikte gelir ve .NET platformu için entegre bir şekilde çalışır. MSTest, basit ve kullanımı kolaydır, ancak bazı geliştiriciler tarafından diğer çerçevelere kıyasla daha az esnek bulunabilir.

Bu birim test çerçeveleri, C# ve .NET platformunda yazılım geliştirme projelerinde kullanılan yaygın araçlardır. Projenizin gereksinimlerine ve tercihlerinize bağlı olarak en uygun olanı seçebilirsiniz.

***

## xUnit ile Test Yazma Ornegi

xUnit.net, C# ve .NET için modern bir birim test çerçevesidir. Basit ve temiz bir yapıya sahiptir ve genellikle .NET Core ve .NET 5 gibi yeni .NET platformlarında tercih edilir. İşte bir xUnit.net testi yazma ve açıklama örneği:

## Örnek Senaryo

Varsayalım ki, bir hesap makinesi uygulaması geliştiriyorsunuz ve toplama işleminin doğru çalışıp çalışmadığını test etmek istiyorsunuz.

## Test Sınıfı ve Metodu Oluşturma

```csharp
using System;
using Xunit;

public class CalculatorTests
{
    [Fact]
    public void Add_WhenAddingTwoNumbers_ReturnsCorrectResult()
    {
        // Arrange
        int num1 = 5;
        int num2 = 10;
        Calculator calculator = new Calculator();

        // Act
        int result = calculator.Add(num1, num2);

        // Assert
        Assert.Equal(15, result);
    }
}
```
## Açıklama

Bu test senaryosunda, `Calculator` sınıfının `Add` metodunun iki sayıyı doğru bir şekilde topladığını doğruluyoruz. Bu, uygulamanın temel işlevselliğini kontrol etmemize olanak tanır ve herhangi bir hata olup olmadığını belirler.

xUnit.net ile test yazmak oldukça basit ve okunaklıdır. Her testin üç ana bölümden oluştuğunu unutmamak önemlidir: **Arrange** (hazırlık), **Act** (eylem) ve **Assert** (doğrulama). Bu bölümler, test senaryosunu düzenler, işlevselliği çağırır ve sonucun doğruluğunu kontrol eder.
