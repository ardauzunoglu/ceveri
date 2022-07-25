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


Desteklenen Uzantılar
-------------------------

Desteklenen uzantılar:
#. .txt
#. .json
#. .xlsx

Kullanım
----------------

ÇeVeri kütüphanesi tek bir ana fonksiyondan ve bu fonksiyonun alt fonksiyonlarından faydalanmaktadır.

Desteklenen uzantılardan birine sahip bir dosyayı çevirmek için ``cevir()`` fonksiyonunu kullanabilirsiniz. ``cevir()`` fonksiyonuna ait üç parametre bulunmaktadır. Bu parametrelerden ilki ``file`` parametresi olup, çevrilmesini istediğiniz dosyaya ait dosya yolunu istemektedir. İkinci parametre olan ``save_path`` parametresi ise çevrilen dosyanın kaydedileceği dosya yolunu istemektedir. Üçüncü parametre olan ``source_language`` parametresi zorunlu bir parametre olmayıp çevirinin gerçekleştirileceği kaynak dilin kodunu (dil kodlarına göz atmak için `tıklayınız. <https://cloud.google.com/translate/docs/languages>`_) istemektedir. ``source_language`` parametresine ait bir değer sunulmadığı vakit Google Translate API tarafından otomatik dil tespiti gerçekleştirilecektir.

``file`` parametresine sunulan dosya yolundaki dosyanın uzantısı, desteklenen uzantılar arasında yer almıyorsa bir ``TypeError`` hatası döndürülecektir.

Örnek kullanım:

>>> from ceveri import cevir
>>> cevir("D:/files/ingilizce_dosya.json", "D:/files/cevrilmis_dosya.json", "en")
Dosya başarıyla çevrildi.
Çevrilen dosyaya D:/files/cevrilmis_dosya.json adresinden erişebilirsiniz.

Bir diğer örnek kullanım:

>>> from ceveri import cevir
>>> cevir("D:/files/rusca_dosya.json", "D:/files/turkce_dosya.json")
Dosya başarıyla çevrildi.
Çevrilen dosyaya D:/files/turkce_dosya.json adresinden erişebilirsiniz.