---
title: Notas de la versión
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: En este artículo se describen las mejoras acumulativas de las salas de Microsoft Teams.
ms.openlocfilehash: 8461c3c7f1a3b132e3cabad81eeb211c28e8ef3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288463"
---
# <a name="release-notes"></a>Notas de la versión 

En este artículo se describen las mejoras acumulativas de las salas de Microsoft Teams.


##  <a name="version-history"></a>Historial de versiones

| Prensa | Publicado en <br>Microsoft Store | 
| ---     | ---  |
| 4.0.85.0 | 04/08/2019   |
| 4.0.78.0 | 03/14/2019   |
| 4.0.76.0 | 03/04/2019   |
| 4.0.64.0 | 12/14/2018   |
| 4.0.51.0 | 11/17/2018   | 
| 4.0.31.0 | 10/16/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  08/27/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  06/18/2018    |
| 3.1.113.0|  06/13/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  11/27/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 03/15/2017 | 
| RTM (1.0.8) | 12/7/2016  | 

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Introducción a la característica salas de Microsoft Teams y problemas

### <a name="40850-0482018"></a>4.0.85.0 (04/8/2018)

Introdujo en esta actualización:

- Corrige un problema con la característica "enviar comentarios" 
- Optimizaciones para la preparación de la próxima actualización del dispositivo MTR a Windows 10, versión 1809

### <a name="40780-03142018"></a>4.0.78.0 (03/14/2018)

Introdujo en esta actualización:

- Corrección del error "bloqueo en la aplicación" que afectó a los dispositivos de compilación heredada de Windows 10 RS2.  


### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introdujo en esta actualización:

- Teclado DTMF para reuniones P2P de Microsoft Teams y llamadas RTC. Para convertir Microsoft Teams en el cliente de llamadas predeterminado, los administradores deben establecer IsTeamsDefaultClient en true
- Anclar el video entrante de un participante remoto a pantalla completa en la parte delantera de la pantalla. Usar el comando "PIN" de la lista de participantes en la consola
- Mejoras en las notificaciones de sala de reuniones con la adición del anverso de la notificación del salón
- La parte frontal de la pantalla de la sala elimina el icono de conversión cuando la señal Bluetooth no está habilitada en el dispositivo del sistema Room
- Solución de problemas de control de volumen en reuniones de Teams


### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introdujo en esta actualización:

- Mostrar contenido en la parte frontal de las pantallas del salón (para) en los sistemas de la sala de pantalla dual
- Temas y portada de la interfaz de usuario del salón
- Compatibilidad con el cliente de TLS 1,2. En el caso de los clientes locales, la habilitación de communciation a través de TLS 1,2 para salas de Microsoft Teams requiere Skype empresarial Server 2015 cummulative Update 9 (CU9) o Skype para Buisness Server 2019 cummulative Update 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introdujo en esta actualización:

- Soporte de pantalla dual (frontal de habitación) para reuniones de Teams 

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introdujo en esta actualización:

- Correcciones de calidad y confiabilidad

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introdujo en esta actualización:
 
- Cambios de código necesarios para preparar la aplicación salas de Microsoft Teams para versiones posteriores de la actualización 1803 de Windows 10
- Solucionar el problema de formato con los CLUF localizados, específicamente noruego, que evitan el avance más allá de la ventana de configuración de la versión OOBE de CLUF
- Cambios de código necesarios para hacer que la aplicación salas de Microsoft Teams se ejecute en sistemas de salas de Lync heredados. Consulta más información [aquí](https://aka.ms/lrsupgrade).
 
### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
Introdujo en esta actualización:

- El Hotfix para Crestron aplicación que no se inicia, que normalmente sería accesible al pulsar el botón de la aplicación en los dispositivos Crestron SR. Microsoft Team Rooms reinicio de la aplicación necesario después de la instalación de 4.0.19.0. 

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)
Introdujo en esta actualización:

- Mejoras de las características "informar de un problema" en el modo de equipos (equivalente a "enviar comentarios" en el modo de Skype empresarial)
- Habilitar la capacidad de hacer una reserva de los equipos al modo de Skype empresarial para las llamadas SIP
- Mejoras de accesibilidad (narrador, ampliador)
- Reiniciar automáticamente la aplicación cuando sea necesario después de aplicar los cambios de aprovisionamiento XML
- Varias correcciones

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introdujo en esta actualización:
- Esta actualización permite que las reuniones de Skype empresarial *y* de equipos sean compatibles con los dispositivos de los sistemas de la sala.  Teams está desactivado de forma predeterminada una vez que se aplica la actualización.  Los administradores pueden habilitar equipos de forma local en la configuración del dispositivo o a través de una inserción remota de XML.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introdujo en esta actualización:

- Error de dirección corregida observado en algunos sistemas durante el inicio de la aplicación.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)
Introdujo en esta actualización:

- Cambios que permiten a Microsoft administrar con mayor flexibilidad las actualizaciones de Windows.
- No hay cambios en la experiencia del usuario final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introdujo en esta actualización:

- Solución para solucionar problemas de respuesta de la consola en los dispositivos basados en Surface Pro 2017 conectados a dos pantallas de la parte frontal de la sala y a la ingesta de video
- Comprobación automática para asegurarse de que el sistema esté ejecutando el script de aprovisionamiento más reciente.

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introdujo en esta actualización:

- Corregir para mejorar el OSK (teclado en pantalla) en Windows 10 versión 1709-Based Systems
- Mejoras en la preparación para futuras actualizaciones del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introdujo en esta actualización: 

- Aplicación actualizada para mejorar la telemetría.

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introdujo en esta actualización:

- Corrige un problema que puede producir problemas con la combinación de reuniones.
- Arregla un problema que se sabe que provoca la experiencia "bloqueo" del dispositivo.

### <a name="31980--382018"></a>3.1.98.0 (3/8/2018)

Introdujo en esta actualización:

- Correcciones de errores o bloqueos para mejorar la estabilidad
- Compatibilidad con la consola de tamaño variable
- Descarga de procesamiento de audio de periféricos (lista blanca de medios adicionales)
- Optimizaciones que permitirán a los profesionales de ti crear imágenes de do-it usted mismo con Windows 10 versión 1709, actualización de enero y versiones posteriores.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introdujo en esta actualización:
 
- Corrige un problema con la característica "enviar comentarios".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introdujo en esta actualización:

- Compatibilidad con el hardware Dock [serie MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Compatibilidad con [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Resuelve un problema por el que muestra (consola y delante del salón) no puede entrar en el modo de suspensión cuando no hay actividad en el salón.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introdujo en esta actualización:

- Se ejecuta en una tableta Surface Pro (2017)  
- Es compatible con la actualización de Windows 10 Enterprise Creator (idioma inglés, compilación 1703)
- Compatibilidad con hardware de acoplamiento de [Crestron Sr](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Compatibilidad con OEM para controles de entorno (Crestron)

La versión de 64 bits de la edición de aniversario de Windows 10 Enterprise (idioma inglés, versión 1607) ya no se admite en la versión de Microsoft Team Rooms Release 3.0.12.0 (actualización 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introdujo en esta actualización:

- Resuelve los problemas observados al buscar usuarios federados a través del campo de búsqueda participantes. Antes de esta corrección, es posible que los resultados de la búsqueda de usuarios federados externos no se hayan resuelto correctamente y, en su lugar, hayan devuelto resultados incorrectos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introdujo en esta actualización:

- Compatibilidad con dos pantallas (para la paridad del sistema heredado)
- Capacidad de la TI (temas integrados y la capacidad de establecer un tema personalizado)
- Capacidad de proporcionar comentarios para las compilaciones públicas
- Telemetría mejorada sobre la confiabilidad de la combinación de reuniones
- Informes adicionales de OMS
- Capacidad para que el administrador de ti configure dispositivos de forma remota  <!--  - Front-of-Room UX shows room details pre-meeting U2  -->


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introdujo en esta actualización:

- Selección de usuario desde la aplicación de la sala de reuniones: dispositivos USB de audio y vídeo
- Informes de estado de la consola de salón integrados para los clientes que usan Microsoft Operations Management Suite, ahora Azure monitor  

### <a name="release-to-market--1272016"></a>Lanzamiento al mercado (12/7/2016)

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
- Se ejecuta en la tableta Surface Pro 4

<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar el entorno](srs-v2-prep.md)

[Compatibilidad con salas de Microsoft Teams versiones actuales de las sucursales](srs2-lifecycle-support.md)

[Problemas conocidos de las salas de Microsoft Teams](known-issues.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)
