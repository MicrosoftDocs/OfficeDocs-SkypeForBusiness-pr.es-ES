---
title: Notas de la versión
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artículo describen mejoras acumulativas en sistemas de salón de Skype v2.
ms.openlocfilehash: 8de76d085bad4ec8fc7c52c0f46a416d9b1cac82
ms.sourcegitcommit: 0ea63f45cb31852fea6894cc6ffb0ae1ae444e64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30950259"
---
# <a name="release-notes"></a>Notas de la versión 

Este artículo describen mejoras acumulativas en sistemas de salón de Skype v2.


##  <a name="version-history"></a>Historial de versiones

| Lanzamiento | Publicado en <br>Almacén de Microsoft | 
| ---     | ---  |
| 4.0.78.0 | 14/03/2019   |
| 4.0.76.0 | 04/03/2019   |
| 4.0.64.0 | 14/12/2018   |
| 4.0.51.0 | 17/11/2018   | 
| 4.0.31.0 | 16/10/2018   | 
| 4.0.27.0 |  1/10/2018    | 
| 4.0.19.0 |  31/08/2018    |   
| 4.0.18.0 |  27/08/2018    |   
| 4.0.8.0 |  06/07/2018    |   
| 3.1.115.0|  18/06/2018    |
| 3.1.113.0|  13/06/2018    |   
| 3.1.112.0|  05/06/2018    |   
| 3.1.104.0|  16/04/2018    |            
| 3.1.100.0|  16/03/2018    |            
| 3.1.99.0 | 14/3/2018      |  
| 3.1.98.0    | 8/3/2018    |   
|  3.0.16.0    |  27/11/2017   |
| 3.0.15.0 | 3/10/2017  |            
| 3.0.12.0 |  1/9/2017  |            
| 3.0.8.0 | 16/11/2017 | 
| 3.0.6.0 | 16/11/2017 | 
| 2.0.2.0  | 15/03/2017 | 
| RTM (1.0.8) | 7/12/2016  | 


## <a name="skype-room-systems-v2-feature-introduction-and-issue-resolution"></a>Sistemas de salón de Skype v2 característica introducción y su resolución


### <a name="40780-03142018"></a>4.0.78.0 (14/03/2018)
Se introdujeron en esta actualización:
- Corrección para el error "se bloquee en el inicio de aplicación" que afectadas dispositivos en la compilación de Windows 10 RS2 heredada.  


### <a name="40760-03042019"></a>4.0.76.0 (04/03/2019)
Se introdujeron en esta actualización:
- Teclado DTMF para las reuniones de Microsoft P2P de los equipos y las llamadas de RTC. Para hacer que Microsoft Teams su cliente que llama de forma predeterminada, los administradores deben establecer IsTeamsDefaultClient en true
- Anclar el vídeo entrante de un participante remoto a pantalla completa en la parte frontal de la presentación de la sala. Use el comando de "Anclar" desde la lista de participantes en la consola
- Mejoras a las notificaciones de la sala de espera con la incorporación de notificación frontal de salón
- Parte frontal de la presentación del salón quita icono de conversión de tipos cuando baliza Bluetooth no está habilitada en el dispositivo de sala de sistema
- Corrección para el problema de control de volumen en las reuniones de los equipos


### <a name="40640-12142018"></a>4.0.64.0 (14/12/2018)
Se introdujeron en esta actualización:
- Mostrar el contenido en ambas front-sala de (muestra en los sistemas de la sala de pantalla dual para)
- Creación de temas y front-sala de mejoras de la interfaz de usuario
- Compatibilidad en el lado de cliente de TLS 1.2. Para en los clientes in situ, habilitar Threats a través de TLS 1.2 para V2 de Skype salón del sistema requiere Skype para Business Server 2015 Cummulative actualización 9 (la actualización acumulativa 9) o Skype para negocio Server 2019 Cummulative Update 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (17/11/2018)
Se introdujeron en esta actualización:
- Compatibilidad con pantalla dual (frontal de sala) para las reuniones de los equipos 

### <a name="40310-10162018"></a>4.0.31.0 (16/10/2018)
Se introdujeron en esta actualización:
- Revisiones de calidad y la confiabilidad 

### <a name="40270-1012018"></a>4.0.27.0 (1/10/2018)
Se introdujeron en esta actualización: 
- Cambios de código necesarios para preparar la aplicación SRSv2 para la actualización de Windows 10 versión 1803 posterior
- Solucionar problema de formato con localizados CLUF - específicamente noruego -, lo que impide que avanzar más allá de la ventana del programa de instalación de OOBE EULA
- Cambios en el código necesarios para hacer que la aplicación v2 de sistemas de salón de Skype ejecutar en los sistemas heredados de salón de Lync. Vea más información [aquí](https://aka.ms/lrsupgrade).
 

### <a name="40190-8312018"></a>4.0.19.0 (31/8/2018)
Se introdujeron en esta actualización: 
- Revisión para la aplicación de Crestron no iniciar que suelen estar accesibles al presionar el botón de la aplicación en los dispositivos Crestron SR. SRSv2 aplicación debe reiniciarse después de la instalación de 4.0.19.0 

### <a name="40180-08272018"></a>4.0.18.0 (27/08/2018)
Se introdujeron en esta actualización: 
- Mejoras en la característica "Un problema de informes" en el modo de los equipos (equivalente de "Enviar comentarios" en Skype para el modo de negocio)
- Habilitar capacidad para reserva desde los equipos de Skype para el modo empresarial para las llamadas SIP
- Mejoras de accesibilidad (Narrador, Ampliador)
- Reiniciar automáticamente la aplicación cuando sea necesario después de que se han aplicado los cambios de aprovisionamiento de XML
- Revisiones de varias

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)
Se introdujeron en esta actualización: 
- Esta actualización permite ambos Skype para profesionales *y* los equipos las reuniones soporte en dispositivos de sistemas de las salas.  Los equipos está desactivado de forma predeterminada una vez que se aplica la actualización.  Los administradores pueden permiten a los equipos localmente en configuración del dispositivo o a través de una inserción xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (18/06/2018)
Se introdujeron en esta actualización: 
- Corrección de error de dirección observada en algunos sistemas durante el inicio de la aplicación.

### <a name="311130-06132018"></a>3.1.113.0 (13/06/2018)
Se introdujeron en esta actualización: 
- Habilitación de Microsoft más flexible de cambios administración las actualizaciones de Windows.
- Ningún cambio en la experiencia del usuario final.

### <a name="311120-06052018"></a>3.1.112.0 (05/06/2018)
Se introdujeron en esta actualización: 
- Corrección de la capacidad de respuesta consola de dirección ingesta problemas observados en dispositivos basados en 2017 Surface Pro conectados a dos pantallas de la parte frontal de la sala y vídeo
- Verificación automatizado para asegurarse de que el sistema está ejecutando aprovisionamiento más reciente de la secuencia de comandos.

### <a name="311040-04162018"></a>3.1.104.0 (16/04/2018)
Se introdujeron en esta actualización: 
- Corrección para mejorar OSK (teclado en pantalla) comportamiento en sistemas basados en la ventana de 10 versión 1709
- Mejoras realizadas a prepararse para las actualizaciones futuras del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (16/03/2018)
Se introdujeron en esta actualización:  
- Aplicación que se ha actualizado para mejorar la telemetría.

### <a name="31990-03142018"></a>3.1.99.0 (14/03/2018)
Se introdujeron en esta actualización: 
- Es posible que se producen las revisiones de un problema donde reunión intermitente unirse a problemas.
- Soluciona un problema conocido como resultado una experiencia de bloqueo"dispositivo".

### <a name="31980--382018"></a>3.1.98.0 (8/3/2018)
Se introdujeron en esta actualización: 
- Errores/correcciones para mejorar la estabilidad de bloqueo
- Compatibilidad con la consola de tamaño variable
- Procesamiento de audio periférico descarga (lista blanca de medios adicionales)
- Optimizaciones que permiten a los profesionales de TI crear imágenes personal con la actualización de enero de Windows 10 versión 1709 y versiones posteriores.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (27/11/2017)
Se introdujeron en esta actualización:  
- Soluciona un problema con la característica "Enviar comentarios".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)
Se introdujeron en esta actualización: 
- Soporte para la [Serie de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) acopla hardware
- Soporte técnico para la [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Resuelve un problema donde muestra (consola y plano de sala) producirá un error de entrar en modo de suspensión cuando no hay ninguna actividad en la sala.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)
Se introdujeron en esta actualización:   
- Se ejecuta en una tableta Surface Pro (2017)  
- Admite la actualización del creador de Windows 10 Enterprise (en inglés, compilación 1703)    
- Soporte para [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) acopla hardware    
- Soporte técnico de OEM para controles del entorno (Crestron)
    
Ya no se admite la versión de 64 bits de edición de Windows 10 Enterprise aniversario (en inglés, versión 1607) a partir de sistemas de salón de Skype v2 versión 3.0.12.0 (actualización 3). 

### <a name="3080-842017"></a>3.0.8.0 (4/8/2017) 
Se introdujeron en esta actualización: 
- Resuelve problemas observados cuando busca federados a los usuarios a través del campo de búsqueda de los participantes. Anterior a esta revisión, los resultados de búsqueda para los usuarios federados externos es posible que no tiene resuelven correctamente y en su lugar devuelve resultados incorrectos. 

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 
Se introdujeron en esta actualización: 
- Compatibilidad con pantalla dual (para la paridad de sistemas heredados)   
- Themability (temas integrados y la capacidad para establecer tema personalizado) 
- Capacidad de proporcionar comentarios para compilaciones públicas     
- Telemetría mejorada alrededor de confiabilidad de unirse a la reunión     
- Creación de informes de OMS adicionales     
- Capacidad de administración de TI configurar los dispositivos de forma remota  <!--  - Front-of-Room UX shows room details pre-meeting U2  --> 


### <a name="2020-03152017"></a>2.0.2.0 (15/03/2017)
Se introdujeron en esta actualización: 
- Selección de usuario en la aplicación de los dispositivos USB de audio y vídeos de sala de la reunión
- Salón integrada consola informes de estado de los clientes que usen Microsoft Operations Management Suite, ahora Monitor de Azure  

### <a name="release-to-market--1272016"></a>Versión en el mercado (7/12/2016)
**Características:** 

 **Creado para Skype Empresarial**
  
- Un solo toque para unirse a reuniones de Skype.    
- La experiencia de las reuniones de Skype optimizada para salas con prestaciones de audio HD de banda ancha y vídeo HD en toda la pantalla.
- Todos los participantes se pueden conectar a la reunión de Skype mediante el dispositivo que elijan desde el lugar en el que se encuentren.
- Invite a las personas desde su directorio, donde podrá consultar su disponibilidad en ese mismo momento o a través de una llamada de teléfono.
- Es compatible con los servicios de conferencias RTC y llamadas RTC de Skype Empresarial como sustitución del teléfono de conferencias independiente de su sala.
    
  **Transforme cualquier sala de reuniones**
  
- Una aplicación de reuniones de Skype dedicada y optimizada para el controlador táctil situado en el centro de la mesa y las pantallas frontales de gran tamaño.
- Permite aprovechar las inversiones que ya ha realizado en pantallas frontales o proyectores.
- Funciona en todo tipo de áreas de reuniones, desde los espacios más apiñados a las salas de conferencias más amplias.
- Los dispositivos de audio y vídeo certificados de Skype Empresarial están disponibles para diversos tamaños de salas.
- Transmisión por cable integrada para compartir el escritorio del proyecto con la sala y con la reunión de Skype.
    
  **Fácil de implementar, sencillo de administrar.**
  
- Un dispositivo que está encendido en todo momento y que activará automáticamente las pantallas cuando detecte que hay alguna persona en la sala.
- Sencilla implementación y actualización de la aplicación de reuniones de Skype para UWP (Plataforma universal de Windows).
- Windows AppLocker bloquea el dispositivo con la aplicación de reuniones de Skype.
- Se supervisa y se administra como un dispositivo con Windows 10 Enterprise mediante Intune y SCCM (MDM).
- Fiabilidad de carácter empresarial.
- La formación que requieren los usuarios es muy poca puesto que ya conocen la interfaz de usuario de Skype.
- Se ejecuta en tablet Surface Pro 4
 

<a name="See"> </a>  
## <a name="see-also"></a>Consulte también

[Ayuda de la versión 2 de sistemas de salón de Skype](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar su Skype para el entorno empresarial](srs-v2-prep.md)

[Compatibilidad con sistemas de salas de Skype v2 actuales sucursal versiones](srs2-lifecycle-support.md)

[Problemas conocidos de v2 de sistemas de salón de Skype](../../manage/skype-room-systems-v2/known-issues.md)

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)

[Administrar Sistemas de salas de Skype v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
