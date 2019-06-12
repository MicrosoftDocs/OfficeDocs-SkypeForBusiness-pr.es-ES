---
title: Planear clientes de reuniones (aplicación web y aplicación reuniones)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumen: los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación Web de Skype empresarial y la aplicación reuniones de Skype mientras planea Skype empresarial Server. Este artículo no está dirigido a los usuarios de estas aplicaciones.'
ms.openlocfilehash: a2bc418b9179a63452c5d4fdd1990676f9db4b14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277317"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planear clientes de reuniones (aplicación web y aplicación reuniones)
 
**Resumen:** Los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación Web de Skype empresarial y la aplicación reuniones de Skype mientras planea Skype empresarial Server. Este artículo no está dirigido a los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype empresarial Server, los usuarios de la organización tendrán el cliente de Skype para empresas instalado como parte del proceso de implementación. 
  
Más adelante, los usuarios pueden crear reuniones e invitar a usuarios externos a la organización, y las invitaciones a reuniones no pueden tener ninguna versión del cliente de Skype empresarial. Cuando los usuarios hagan clic en la dirección URL de la invitación a la reunión, la falta de un cliente se detectará y el invitado sin un cliente de Skype empresarial se le pedirá que descargue e instale un solo cliente de reuniones y ligeros para que puedan unirse a la reunión.
  
> [!NOTE]
> La aplicación Web de Skype empresarial y la aplicación reuniones de Skype solo están disponibles cuando se intenta iniciar sesión en una reunión sin tener Skype empresarial. La ayuda del usuario para estas aplicaciones [https://aka.ms/smahelp](https://aka.ms/smahelp)está en. 
  
> [!NOTE]
> No puede preinstalar la aplicación Web de Skype empresarial ni la aplicación reuniones de Skype, pero [Smart Phone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y los usuarios de [tabletas](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) pueden instalar clientes móviles económicos que pueden usar para asistir a las reuniones.
  
De forma predeterminada, el servidor que hospeda la reunión indicará al usuario que descargue e instale la aplicación Web de Skype empresarial para unirse a la reunión. La aplicación Web de Skype empresarial se almacena en el servidor front-end y se envía al asistente de la reunión. 
  
Para Skype empresarial Server, la aplicación reuniones de Skype (en Windows) y Skype empresarial para Mac (en Mac) están disponibles como reemplazos de la aplicación Web de Skype empresarial a partir de CU5, pero proporcionar las aplicaciones de reemplazo requiere la configuración adicional. se describe en [Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si la aplicación reuniones de Skype y Skype empresarial para Mac están habilitadas, los usuarios descargarán la versión más reciente de las aplicaciones de la red de entrega de contenido (CDN) de Office 365 en lugar de hacerlo desde Skype empresarial Server. Para Skype empresarial Server 2019, usar la aplicación reuniones de Skype y Skype empresarial para Mac es la única opción.
  
La aplicación reuniones de Skype ofrece una experiencia de explorador simplificada para descargar e instalar la aplicación y unirse a reuniones, incluida una unión con un solo clic para los usuarios de Internet Explorer. La aplicación reuniones de Skype también tiene muchas mejoras en la aplicación Web de Skype empresarial para la confiabilidad y la experiencia de reunión. 
  
> [!NOTE]
> A partir de Skype empresarial Server 2015 CU5 o versiones posteriores, las reuniones que se celebran con Skype empresarial online ya no enviarán a un usuario sin cliente la aplicación Web de Skype empresarial, sino que se les enviará en su lugar la aplicación reuniones de Skype (en Windows) o Skype empresarial para Mac (en Mac). A partir de Skype empresarial Server 2015 CU5 o posterior, si [habilita la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), los usuarios sin clientes recibirán la aplicación reuniones de Skype o Skype empresarial para Mac en lugar de la aplicación Web de Skype empresarial. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar la aplicación Web de Skype empresarial, un usuario debe tener una de las siguientes combinaciones de sistema operativo y explorador compatibles. 
  
**Sistema operativo y compatibilidad mínima del explorador para la aplicación Web de Skype empresarial**

| Sistema operativo | Perimetral | Internet Explorer 11 o posterior en 32 y 64 bits | 32 y 64 de bits de Internet Explorer 10 o posterior | Internet Explorer 9 o posterior de 32 y 64 bits | 32-y 64-bit versión de Safari 6.2.8-11. X | 32 y 64 bits de Chrome 18. X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí   <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 8,1 &#x2776; <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sí &#x2778; <br/> |
|&#x2776; de Windows 8 (basado en Intel) <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |Sí   <br/> |Sí  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|macOS 10,8 y versiones posteriores (basadas en Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí <br/> |
   
&#x2776; el complemento del explorador de la aplicación Web de Skype empresarial requiere un complemento de uso compartido específico para usar voz, vídeo, uso compartido y visualización de pantalla continua y otras características basadas en el equipo. A un asistente para una reunión se le ofrece la opción de instalar el complemento para compartir al unirse a la reunión o al iniciar una de estas características. En Windows 8 y Windows 8,1, el complemento para compartir solo se puede instalar si está ejecutando Internet Explorer 10 o Internet Explorer 11 para el escritorio. Estas características no están disponibles con las versiones de Internet Explorer 10 y 11 que no son de escritorio. Tenga en cuenta que Firefox y Safari versión 12,0 y posteriores ya no se admiten.
  
&#x2777; en sistemas operativos Windows 7, Windows Server 2008 R2 y Macintosh compatibles, todas las características están disponibles, como la voz, el vídeo, la visualización de aplicaciones, el uso compartido de aplicaciones, la visualización de escritorio y el uso compartido de escritorio basados en equipos. Para usar estas características, necesita instalar un complemento cuando se le indique. No olvide que la versión 10.7 de Mac OS X ya no es compatible.
  
&#x2778; el acceso a la aplicación web desde Chrome en Windows iniciará un pequeño programa que cargará la aplicación web en un marco incrustado de Internet Explorer. Este programa requiere la instalación de una de las versiones compatibles de Internet Explorer para que la aplicación web se cargue correctamente.
  
> [!NOTE]
> Los usuarios de Office 365 pueden usar Internet Explorer 10 o una versión posterior con Skype empresarial. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

La aplicación reuniones de Skype se ejecuta como una aplicación en los equipos que usan Windows 10, Windows 8,1, Windows 8, Windows 7, con la versión 32 64 de Internet Explorer 11 o posterior instalada. 
  
Para cualquier otra dependencia, consulte [plataformas compatibles con la aplicación reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype empresarial para Mac

Skype empresarial para Mac se ejecuta en equipos con macOS versión 10,8 o posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, auriculares con micrófono o un dispositivo equivalente compatible con el equipo. Las características de vídeo necesitan un dispositivo de vídeo compatible con el equipo. Para obtener información detallada sobre la compatibilidad de hardware de video y la calidad de video prevista, consulte [resoluciones de video para clientes de Skype empresarial](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de la aplicación Web de Skype empresarial o de la aplicación reuniones de Skype experimenta problemas de conexión con la reunión, lo más probable es que la infraestructura de red de su organización no esté configurada para admitir Office 365, como se describe en [office 365 direcciones URL e intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esto sucede si la reunión fue creada por un usuario de Skype empresarial online o de Skype empresarial Server. 
  
Si el usuario se encuentra en una red que no está configurada como se ha descrito, muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión.
  
## <a name="supported-meetings-features"></a>Características de reuniones compatibles
<a name="BKMK_Conferencing"> </a>

En esta tabla se comparan las características de las reuniones disponibles para los usuarios del cliente de Skype empresarial, la aplicación Web de Skype empresarial, la aplicación reuniones de Skype y Lync Web App. Lync Web App se muestra con fines de comparación de características: un usuario solo puede descargar y usar Lync Web App si la reunión se ha hospedado en un servidor de Lync 2013.

| Característica/función | Cliente de Skype empresarial 2016 o 2019 | Skype empresarial en un cliente para Mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Agregar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Cambiar el audio a un teléfono para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cambiar el audio a un teléfono para participantes de invitados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Ver un vídeo entre varias partes (vista de galería)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pantalla compartida basada en vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (solo lectura)  <br/> |||
|Usar los controles de moderador en la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a lista de reuniones detallada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Establecer mensajes de mensajería instantánea como de importancia alta  <br/> |&#x2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Compartir un programa (si se habilita)  <br/> |&#x2714;||&#x2714; (solo en Windows; requiere complemento)  <br/> |&#x2714; (solo en Windows; requiere complemento)  <br/> |&#x2714; (solo en Windows; requiere complemento)  <br/> |
|Tomar el control del escritorio o programa compartido de otro usuario  <br/> |&#x2714;||&#x2714; (solo &#x2776; en Windows; requiere complemento)  <br/> |&#x2714; (solo &#x2776; en Windows; requiere complemento)  <br/> |&#x2714; (solo &#x2776; en Windows; requiere complemento)  <br/> |
|Permitir que otro usuario tome el control de su escritorio o programa compartidos  <br/> |&#x2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por nombre  <br/> |&#x2714;|&#x2714;||||
|Invitar a participantes por número de teléfono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por correo electrónico  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniones de audio de acceso telefónico local  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Empezar una reunión de tipo Reunirse ahora  <br/> |&#x2714;|&#x2714;||||
|Grabar una reunión  <br/> |&#x2714;|||||
|Agregar y descargar datos adjuntos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Explorar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar y editar las notas de reunión de OneNote  <br/> |&#x2714;||Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |
|Usar una pizarra  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar sondeos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Cargar archivos para compartir con otros usuarios  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programar una reunión o conferencia  <br/> |Programador web de Outlook o Skype empresarial  <br/> |Programador web de Outlook o Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |
|Un&amp;administrador de preguntas y respuestas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Deshabilitar vídeo de asistentes  <br/> |&#x2714;|||||
|Deshabilitar la mensajería instantánea de la reunión  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Silenciar audiencia  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convertir a todos en asistentes  <br/> |&#x2714;|||||
|Producir difusión de reunión de Skype  <br/> |&#x2714;|||||
   
 &#x2776; los participantes no pueden controlar los escritorios compartidos por usuarios de Skype empresarial para Mac, Lync para Mac 2011 o Communicator para Mac 2011. Esto tampoco funcionará en la aplicación Web de Skype empresarial en Max OSX.
  
 &#x2777; para Skype empresarial online, esta característica requiere conferencias RTC de Microsoft, mensajería unificada de Exchange o un proveedor de servicios de audioconferencia de terceros.
  
 &#x2778; el cliente de Lync para Mac 2011 no puede ver presentaciones de PowerPoint de Microsoft Office 2013 cuando se han compartido en una conferencia desde la aplicación Web de Skype empresarial.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, la [ayuda en línea](https://aka.ms/smahelp) para estas aplicaciones está disponible fácilmente. Los profesionales de TI deben tener en cuenta los siguientes problemas:
  
- Si el usuario está en una red que no está configurada para cumplir los [requisitos de red](meetings-clients.md#Network), muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión.
    
- Es posible que algunos usuarios tengan equipos administrados por la empresa con permisos deshabilitados para instalar aplicaciones. para esos usuarios, ninguna de las aplicaciones es una opción, pero [Smart Phone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y los usuarios de [tabletas](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) pueden instalar clientes móviles económicos que pueden usar para asistir a las reuniones.
    
    En los [temas de ayuda](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)también se tratan otros problemas de instalación. 
    
- Los usuarios pueden ver una advertencia de Firewall la primera vez que ejecutan la aplicación reuniones. Es posible que se le pida que abran los puertos para optimizar la experiencia y esto puede requerir privilegios de administrador en el equipo que no tengan. La aplicación debe seguir funcionando y el usuario puede rechazar la apertura de los puertos solicitados de manera segura. 
    
- Debe tener [ActiveX habilitado sin filtrar](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en Internet Explorer, incluso si IE no es el explorador predeterminado. En la aplicación Web de Skype empresarial, es necesario un control ActiveX, un pequeño módulo que agrega características adicionales a una aplicación web u otro programa, para compartir audio, vídeo y pantalla.
    
- Para que algunas de las características de la aplicación Web de Skype empresarial funcionen correctamente, debe permitir que el explorador [guarde](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) las cookies en el equipo o dispositivo.
    
- Es posible que tenga que activar la compatibilidad con [JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) en el explorador para que algunas características de la aplicación Web de Skype empresarial funcionen de la forma esperada.
    
### <a name="aes-support"></a>Compatibilidad con AES 

A partir de Skype empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4,6 y esto puede provocar errores en la aplicación reuniones de Skype. [Los requisitos criptográficos de ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) tienen más detalles.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Implementar clientes descargables en Internet en Skype empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas compatibles con la aplicación reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
