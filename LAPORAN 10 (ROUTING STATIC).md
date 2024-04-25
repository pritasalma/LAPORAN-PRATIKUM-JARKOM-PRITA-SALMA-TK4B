# KONFIGURASI ROUTING STATIC

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/b6091010-e944-43a6-b333-2846bb752f47)


Berikut ini adalah langkah-langkah pengerjaanya

**1. Buat topologi rangkaiannya di cisco packet tracer seperti dibawah ini**

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/d1a67987-2299-4376-829a-93fb8912f8cc)


**2. Jangan lupa untuk memasukkan IP pada masing-masing perangkat seperti berikut ini**

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/13e8bd9c-d0b1-4b25-a490-8b40294a5d30)


>> Cara memasukkan IP pada perangkat router
>>
>> 1. Pilih terlebih dahulu router mana yang ingin dimasukkan IP, lalu lakukan langkat berikut ini (dibawah ini adalah contoh pada router 3)
>>    
>> ![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/f1c1ba7e-a4c2-4290-ac69-b3e17e5a83ec)
>>
>> 2. Lalu, lanjutkan ke pengisian program saat semua perangkat sudah tersambung
>>
>> ![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/b8fdc0e8-c05c-4611-a7af-64d80f88e8f7)


**3. Masukkan program sebagai berikut pada masing-masing router yang ada**
>> Berikut ini adalah cara pengisian programnya
>>
>> ![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/15be107d-e51e-44ec-a0d8-6e944fcbe567)
>>
>> Lalu, lanjutkan pengisian programnya pada masing-masing perangkat Router, dengan program sebagai berikut ini :
>> #
>> **ROUTER 1**
>>
>>  Konfigurasi Static Routing :
>>
>>     ROUTER_I (config)#ip route 192.168.20.0 255.255.255.0 10.10.10.2
>>     ROUTER_I (config)#ip route 10.20.10.0 255.255.255.252 10.10.10.2
>>     ROUTER_I (config)#ip route 192.168.40.0 255.255.255.0 10.10.10.2
>>
>> Konfigurasi Default Routing :
>>
>>     ROUTER_I(config)#ip route 0.0.0.0 0.0.0.0 10.10.10.2
>> 
>> Konfigurasi Routing Dynamic RIPv2 :
>>
>>     ROUTER_I(config)#router rip
>>     ROUTER_I(config-router)#version 2
>>     ROUTER_I(config-router)#network 192.168.2.0
>>     ROUTER_I(config-router)#network 10.10.10.0
>>
>> #
>> ROUTER 2
>>
>>  Konfigurasi Static Routing :
>>
>>     ROUTER_II (config)#ip route 192.168.2.0 255.255.255.0 10.10.10.1
>>     ROUTER_II (config)#ip route 192.168.40.0 255.255.255.0 10.20.10.2
>>
>> Konfigurasi Default Routing :
>>
>>     ROUTER_II(config)#ip route 0.0.0.0 0.0.0.0 10.10.10.1
>>     ROUTER_II(config)#ip route 0.0.0.0 0.0.0.0 10.20.10.2
>> 
>> Konfigurasi Routing Dynamic RIPv2 :
>>
>>     ROUTER_II(config)#router rip
>>     ROUTER_II(config-router)#version 2
>>     ROUTER_II(config-router)#network 192.168.20.0
>>     ROUTER_II(config-router)#network 10.10.10.0
>>     ROUTER_II(config-router)#network 10.20.10.0
>>
>> #
>> ROUTER 3
>> 
>>  Konfigurasi Static Routing :
>>
>>     ROUTER_III (config)#ip route 192.168.2.0 255.255.255.0 10.20.10.1
>>     ROUTER_III (config)#ip route 10.10.10.0 255.255.255.252 10.20.10.1
>>     ROUTER_III (config)#ip route 192.168.20.0 255.255.255.0 10.20.10.1
>> 
>> Konfigurasi Default Routing :
>>
>>      ROUTER_I(config)#ip route 0.0.0.0 0.0.0.0 10.10.10.2
>> 
>> Konfigurasi Routing Dynamic RIPv2 :
>>
>>     ROUTER_III(config)#router rip
>>     ROUTER_III(config-router)#version 2
>>     ROUTER_III(config-router)#network 192.168.40.0
>>     ROUTER_III(config-router)#network 10.20.10.0
>>
