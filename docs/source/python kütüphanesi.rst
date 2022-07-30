Python Kütüphanesi
=====

.. _kurulum:
.. _kullanım:
.. _desteklenen uzantılar:

Kurulum
------------

ÇeVeri Python kütüphanesini kullanmak için pip kullanabilirsiniz:

.. code-block:: console

   (.venv) $ pip install ceveri

En çok sayıda uzantıyı, en optimize biçimde çevirebilmek için son sürümü kurabilirsiniz:

.. code-block:: console

   (.venv) $ pip install ceveri==1.0.3

Desteklenen Uzantılar
-------------------------

Desteklenen uzantılar: .txt, .json, .xlsx, .csv, .xml, .pkl, ve .docx. 

Sonraki güncellemelerde eklemeyi planladığımız ve güncel olarak üzerinde çalıştığımız uzantılar: .pdf, .tsv, .rtf, .rft, ve .me.

Hangi uzantıyı önceliklendirmemiz konusunda görüşünüzü bildirmek isterseniz :ref:`ÇeVeri Tavsiye ve Değerlendirme Formu<https://docs.google.com/forms/d/e/1FAIpQLSdE6Bn6bazSASLLzCnlWuHokMeH2ZrQYbysyv83nTjgp_K5fQ/viewform>`'nu doldurabilirsiniz. 

Kullanım
----------------

ÇeVeri kütüphanesi tek bir ana fonksiyondan ve bu fonksiyonun alt fonksiyonlarından faydalanmaktadır.

Desteklenen uzantılardan birine sahip bir dosyayı çevirmek için ``cevir()`` fonksiyonunu kullanabilirsiniz. ``cevir()`` fonksiyonuna ait üç parametre bulunmaktadır. Bu parametrelerden ilki ``file`` parametresi olup, çevrilmesini istediğiniz dosyaya ait dosya yolunu istemektedir. İkinci parametre olan ``save_path`` parametresi ise çevrilen dosyanın kaydedileceği dosya yolunu istemektedir. Üçüncü parametre olan ``source_language`` parametresi zorunlu bir parametre olmayıp çevirinin gerçekleştirileceği kaynak dilin kodunu (dil kodlarına göz atmak için `tıklayınız. <https://cloud.google.com/translate/docs/languages>`_) istemektedir. ``source_language`` parametresine ait bir değer sunulmadığı vakit Google Translate API tarafından otomatik dil tespiti gerçekleştirilecektir.

``file`` parametresine sunulan dosya yolundaki dosyanın uzantısı, desteklenen uzantılar arasında yer almıyorsa bir ``TypeError`` hatası döndürülecektir.

Örnek kullanım:

>>> from ceveri import cevir
>>> cevir("D:/files/ingilizce_dosya.json", "D:/files/cevrilmis_dosya.json", "en")
Çeviri işlemi başladı.
Dosya başarıyla çevrildi.
İşlem süresi: 304.320070028305 saniye.
Çevrilen dosyaya D:/files/cevrilmis_dosya.json adresinden erişebilirsiniz.

Bir diğer örnek kullanım:

>>> from ceveri import cevir
>>> cevir("D:/files/rusca_dosya.txt", "D:/files/turkce_dosya.txt")
Çeviri işlemi başladı.
Dosya başarıyla çevrildi.
İşlem süresi: 275.215596311885 saniye.
Çevrilen dosyaya D:/files/turkce_dosya.txt adresinden erişebilirsiniz.
