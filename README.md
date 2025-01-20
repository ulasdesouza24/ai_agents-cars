# NEAT Self-Driving Car AI

Bu proje, NEAT (NeuroEvolution of Augmenting Topologies) algoritması kullanılarak kendini eğiten bir araç AI simülasyonudur. Araçlar farklı pistlerde sürüş yapmayı öğrenebilir ve her nesilde daha iyi performans göstermeye çalışır.

## Özellikler

- Çoklu pist seçeneği (Basic, Imola, Silverstone, Monza)
- Mouse ile özel başlangıç noktası seçimi
- Araç yönünü ok tuşlarıyla ayarlama
- Gerçek zamanlı fitness grafiği
- NEAT algoritması ile yapay zeka eğitimi
- Çarpışma algılama sistemi
- Radar sistemi ile mesafe ölçümü

## Gereksinimler

```bash
Python 3.x
pygame
neat-python
matplotlib
```

## Kurulum

1. Repository'yi klonlayın:
```bash
git clone [repository-url]
cd self-driving-car-ai
```

2. Gerekli kütüphaneleri yükleyin:
```bash
pip install pygame neat-python matplotlib
```

3. Assets klasörünün içinde aşağıdaki dosyaların olduğundan emin olun:
- track.png (Basic pist)
- imola.png (Imola pisti)
- silverstone.png (Silverstone pisti)
- monza.png (Monza pisti)
- car.png (Araç görseli)

## Kullanım

1. Programı çalıştırın:
```bash
python main.py
```

2. Pist seçim menüsünden bir pist seçin

3. Basic pist dışındaki pistler için:
   - Mouse ile başlangıç noktasını seçin
   - Ok tuşları ile araç yönünü ayarlayın
   - Enter ile onaylayın

4. AI eğitimi başlayacak ve fitness grafiği gerçek zamanlı olarak güncellenecektir

## NEAT Konfigürasyonu

`config.txt` dosyası NEAT algoritmasının parametrelerini içerir:
- Popülasyon büyüklüğü
- Mutasyon oranları
- Türler arası ayarlar
- Ağ yapısı ayarları

## Fitness Hesaplaması

Araçların fitness değeri şu faktörlere göre hesaplanır:
- Kat edilen mesafe (pozitif puan)
- Yaşam süresi (pozitif puan)
- Çarpışma (negatif puan)
- Aşırı dönüş (negatif puan)
- Minimum ilerleme kontrolü (negatif puan)

## Projeyi Özelleştirme

### Yeni Pist Ekleme
1. Pist görselini Assets klasörüne ekleyin
2. TRACKS sözlüğüne yeni pisti ekleyin:
```python
"YeniPist": {
    "image": pygame.transform.scale(pygame.image.load("Assets/yeni_pist.png"), (SCREEN_WIDTH, SCREEN_HEIGHT)),
    "start_pos": None,
    "start_angle": 0,
}
```

### Pencere Boyutunu Değiştirme
`SCREEN_WIDTH` ve `SCREEN_HEIGHT` değişkenlerini istediğiniz değerlerle güncelleyin:
```python
SCREEN_WIDTH = 800  # İstediğiniz genişlik
SCREEN_HEIGHT = 600 # İstediğiniz yükseklik
```

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için `LICENSE` dosyasına bakın.

## Katkıda Bulunma

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/AmazingFeature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add some AmazingFeature'`)
4. Branch'inizi push edin (`git push origin feature/AmazingFeature`)
5. Pull Request oluşturun
