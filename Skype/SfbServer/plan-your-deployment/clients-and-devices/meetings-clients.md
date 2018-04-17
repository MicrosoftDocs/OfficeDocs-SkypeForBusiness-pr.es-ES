---
title: Plan para clientes de reuniones (Web App y App de reuniones)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumen: Los profesionales de TI deben revisar los requisitos de soporte técnico para el Skype para Business Web App y App de reuniones de Skype al planear Skype para Business Server 2015. Este artículo no está pensado para los usuarios de estas aplicaciones.'
ms.openlocfilehash: 4cbfead665d6e325d43f274311d44b5dc48d712e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Plan para clientes de reuniones (Web App y App de reuniones)
 
**Resumen:** Los profesionales de TI deben revisar los requisitos de soporte técnico para el Skype para Business Web App y App de reuniones de Skype al planear Skype para Business Server 2015. Este artículo no está pensado para los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype para Business Server, los usuarios de su organización probablemente tendrá el Skype para Business client instalado como parte del proceso de implementación. 
  
Más adelante esos usuarios pueden crear reuniones e invitar a los usuarios externos a la organización y los invitados a la reunión no tenga ninguna versión de la Skype para cliente de empresa. Cuando los usuarios haga clic en la dirección URL de la invitación a la reunión, se detectará la falta de un cliente y el invitado sin un Skype para Business client le pedirá que descargue e instale a un cliente ligero, las reuniones para que puedan unirse a la reunión.
  
> [!NOTE]
> El Skype para el negocio de la aplicación Web y la aplicación de las reuniones de Skype sólo están disponibles cuando se intenta iniciar sesión en una reunión sin tener un Skype para el negocio. Ayuda de estas aplicaciones está en [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> No puede instalar cualquiera el Skype para Business Web App o App de Skype reuniones previamente, pero los usuarios de [teléfonos inteligentes](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y [Tablet PC](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) pueden instalar a económicos clientes móviles que se pueden usar para asistir a reuniones.
  
De forma predeterminada, el servidor que aloja la reunión dirige al usuario a descargar e instalar Skype para Business Web App para unirse a la reunión. El Skype para el negocio de la aplicación Web se almacena en el servidor Front-End y se envía a asistentes a la reunión. 
  
A partir de Skype para Business Server CU5, Skype reuniones App está disponible como un sustituto de Skype para el negocio de la aplicación Web, pero que proporciona la aplicación de las reuniones de Skype requiere la configuración adicional que se describe en [Habilitar la aplicación Skype reuniones para reemplazar Skype para Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Si está habilitada la aplicación de las reuniones de Skype, los usuarios descargarán la última versión de la aplicación desde el Office 365 Content Delivery Network (CDN) en lugar de desde su Skype para Business server.
  
Skype App de reuniones ofrece una experiencia de explorador simplificada para la descarga e instalación de la aplicación y unirse a reuniones, incluyendo la combinación de un solo clic para que los usuarios de Internet Explorer. Skype reuniones App también tiene muchas mejoras sobre theSkype para el negocio de la aplicación Web para la confiabilidad y la experiencia de la reunión. 
  
> [!NOTE]
> A partir de Skype para Business Server 2015 CU5 o posterior, reuniones mantenidas con Skype para los negocios en línea no volverá a enviar un usuario el Skype para el negocio de la aplicación Web, en su lugar enviarán Skype App de reuniones. A partir de Skype para Business Server 2015 CU5 o una versión posterior, si [Habilitar la aplicación Skype reuniones para reemplazar Skype para el negocio de la aplicación Web (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), los usuarios ser enviado Skype App de reuniones en lugar de Skype para el negocio de la aplicación Web. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para utilizar el Skype para Business Web App, un usuario debe haber uno de los siguientes admite combinaciones de navegador y sistema operativo. 
  
**Sistema operativo y navegador mínima compatibilidad con Skype para Business Web App**


| Sistema operativo | Perimetral | Internet Explorer 11 o superior de 32 y 64 bits | Internet Explorer 10 o posterior de 32 y 64 bits | Internet Explorer 9 o una versión posterior de 32 y 64 bits | Versión de Firefox de 32 y 64 bits 12.X o posterior | Versión de cromo de 32 y 64 bits 18.X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí & #x 2778; <br/> |
| Windows 8.1 & #x 2776; <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí & #x 2778; <br/> |
| Windows 8 (para Intel) & #x 2776; <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |Sí  <br/> |Sí & #x 2778; <br/> |
|Windows 7 con SP1 & #x 2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |Sí  <br/> |Sí & #x 2778; <br/> |
|Windows Server 2008 R2 con SP1 & #x 2777; <br/> |N/D  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí & #x 2778; <br/> |
|macOS 10,8 y posterior (basado en Intel) & #x 2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí & #x 2779; <br/> |
   
& #x 2776; El Skype para el complemento de explorador de negocio de la aplicación Web requiere un complemento específico para compartir utilizar basado en PC voz, vídeo, uso compartido y visualización de pantalla continuo compartir y otras características. Asistente a una reunión se da la opción de instalar el compartir el complemento cuando se unan a la reunión o cuando inician una de estas características. En Windows 8 y Windows 8.1, el uso compartido de complemento puede instalarse sólo si está ejecutando Internet Explorer 10 u 11 de explorador de Internet para el escritorio. Estas características no se encuentran disponibles con la versión de Internet Explorer 10 o Internet Explorer 11 que no es de escritorio.
  
& #x 2777; En compatibles Windows 7, Windows Server 2008 R2 y los sistemas operativos Macintosh, todas las características están disponibles incluyendo basado en PC voz, vídeo, visualización de la aplicación, compartir aplicaciones, visualización de escritorio y uso compartido de escritorio. Para usar estas características, necesita instalar un complemento cuando se le indique. No olvide que la versión 10.7 de Mac OS X ya no es compatible.
  
& #x 2778; Acceso a la aplicación Web desde Chrome en Windows iniciará un pequeño programa que carga la aplicación Web en un marco de Internet Explorer incrustado. Este programa requiere la instalación de una de las versiones compatibles de Internet Explorer para que la aplicación web se cargue correctamente.
  
& #x 2779; Acceso a la aplicación Web desde Chrome en Mac iniciará un pequeño programa que carga la aplicación Web en un marco de Safari incrustado. Este programa requiere uno de los admitidos pueden instalar versiones de Safari para que la aplicación Web que se carga correctamente.
  
> [!NOTE]
> Los usuarios de Office 365 pueden utilizar Internet Explorer 10 o posterior con Skype para el negocio. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

La aplicación de las reuniones de Skype se ejecuta como una aplicación en equipos que utilicen Windows 10, Windows 8.1, Windows 8, Windows 7, con 32 y 64 bits Internet Explorer 11 o posterior instalado. 
  
La aplicación también ejecuta en Mac OS sistemas operativos 10.10 o posterior sin dependencia del explorador específico. 
  
Con cualquier otra dependencia, se refieren a [las plataformas compatibles para la aplicación de las reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, auriculares con micrófono o un dispositivo equivalente compatible con el equipo. Las características de vídeo necesitan un dispositivo de vídeo compatible con el equipo. Para obtener información detallada acerca de la compatibilidad de hardware de vídeo y la calidad de vídeo esperado, consulte [Skype para resoluciones de vídeo de cliente de empresa](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de Skype para experiencias de negocio Web App o App de Skype reuniones reunión problemas de conexión, lo más probable es la que infraestructura de red de su organización no está configurada para la compatibilidad con Office 365 como se describe en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Éste es el caso si la reunión fue creada por un usuario de Skype para los negocios en línea o Skype para Business Server 2015. 
  
Si el usuario está en una red no configurada como se describe, muchas de las características de la aplicación pueden o no funcionar y es posible que no puedan conectarse a la reunión.
  
## <a name="supported-meetings-features"></a>Características de reuniones compatibles
<a name="BKMK_Conferencing"> </a>

Esta tabla compara las características de reuniones disponibles para los usuarios de Skype, Skype para cliente empresarial para negocios Web App, App de reuniones de Skype y Lync Web App. Lync Web App aparece para fines de comparación de características: un usuario ¿sólo se descarga y el uso Lync Web App si la reunión se alojó en un servidor de Lync de 2013.
  

| Característica / función | Skype para cliente de negocios 2016 | Skype para el negocio en el cliente de Mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar VoIP  <br/> |& #x 2714;|& #x 2714;|& #x 2714;(requires plug-in)  <br/> |& #x 2714;(requires plug-in)  <br/> |& #x 2714;(requires plug-in)  <br/> |
|Agregar vídeo  <br/> |& #x 2714;|& #x 2714;|& #x 2714;(requires plug-in)  <br/> |& #x 2714;(requires plug-in)  <br/> |& #x 2714;(requires plug-in)  <br/> |
|Cambiar audio a un teléfono para participantes autenticados  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Cambiar audio a un teléfono para que los participantes invitados  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|||
|Ver un vídeo entre varios participantes (vista de galería)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Pantalla compartida basada en vídeo  <br/> |& #x 2714;|& #x 2714; (para las reuniones alojadas en Skype sólo para los negocios en línea) <br/> |& #x2714;(View-only)  <br/> |||
|Usar los controles de moderador en la reunión  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Acceder a la lista de reuniones detallada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Establecer mensajes de mensajería instantánea como de importancia alta  <br/> |& #x 2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |& #x 2714;|& #x 2714;|& #x 2714; & #x 2776; (requiere Plug-in)  <br/> |& #x 2714; & #x 2776; (requiere Plug-in)  <br/> |& #x 2714; & #x 2776; (requiere Plug-in)  <br/> |
|Compartir un programa (si se habilita)  <br/> |& #x 2714;||& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |
|Tomar el control del programa o escritorio compartido de otro usuario  <br/> |& #x 2714;||& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |& #x 2714; (en Windows únicamente; requiere Plug-in)  <br/> |
|Permitir que otro usuario tome el control de su escritorio compartido o programa  <br/> |& #x 2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Invitar a los participantes por su nombre  <br/> |& #x 2714;|& #x 2714;||||
|Invitar a participantes por número de teléfono  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Invitar a los participantes por correo electrónico  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Usar reuniones de audio de acceso telefónico local  <br/> |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Empezar una reunión de tipo Reunirse ahora  <br/> |& #x 2714;|& #x 2714;||||
|Grabar una reunión  <br/> |& #x 2714;|||||
|Agregar y descargar datos adjuntos  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Explorar archivos de Microsoft PowerPoint  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Agregar y editar las notas de reunión de OneNote  <br/> |& #x 2714;||Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |
|Usar una pizarra  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Realizar sondeos  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Cargar archivos para compartirlos con otros usuarios  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Programar una reunión o conferencia  <br/> |Outlook o Skype para programador de Web empresarial  <br/> |Outlook o Skype para programador de Web empresarial  <br/> |Skype para el programador Web de negocio  <br/> |Skype para el programador Web de negocio  <br/> |Skype para el programador Web de negocio  <br/> |
|Q&amp;un administrador  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Deshabilitar el vídeo de asistentes  <br/> |& #x 2714;|||||
|Deshabilitar la mensajería instantánea de la reunión  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Audiencia de silencio  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Convertir a todos en asistentes  <br/> |& #x 2714;|||||
|Producir difusión de reunión de Skype  <br/> |& #x 2714;|||||
   
 & #x 2776;  Los participantes no pueden controlar los escritorios compartidos por Lync para Mac 2011 o Communicator para usuarios de Mac 2011. Los usuarios de Lync para Mac 2011 y Communicator para Mac 2011 pueden controlar escritorios compartidos por usuarios de Windows. Esto tampoco funcionará con la aplicación web de Skype Empresarial en Mac OS X.
  
 & #x 2777;  Para Skype para los negocios en línea, esta característica requiere Microsoft PSTN conferencias, mensajería unificada de Exchange, o un 3 º proveedor de conferencia de audio.
  
 & #x 2778;  El Lync para Mac 2011 cliente no puede ver las presentaciones de PowerPoint de Microsoft Office 2013 cuando que han sido compartidas en una conferencia por el Skype para el negocio de la aplicación Web.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, está disponible la [Ayuda en línea](https://aka.ms/smahelp) para estas aplicaciones. Los profesionales de TI deben ser conscientes de los problemas siguientes:
  
- Si el usuario no está en una red configurada para satisfacer los [requisitos de la red](meetings-clients.md#Network), muchas de las características de la aplicación pueden o no funcionar y es posible que no puedan conectarse a la reunión.
    
- Algunos usuarios pueden tener equipos corporativos administrados con permiso deshabilitado para instalar aplicaciones. para los usuarios, ni la aplicación es una opción, pero los usuarios de [teléfonos inteligentes](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y [Tablet PC](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) pueden instalar a económicos clientes móviles que se pueden usar para asistir a reuniones.
    
    Otros problemas de instalación también se tratan en los [temas de ayuda](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Los usuarios pueden ver un firewall de advertencia la primera vez ejecutan la aplicación de las reuniones. Se les puede solicitar abrir puertos para optimizar la experiencia, y esto puede requerir privilegios de administrador en el equipo pueden no tener. La aplicación debe funcionar aún y el usuario puede rechazar de forma segura abrir los puertos solicitados. 
    
- Debe tener [ActiveX habilitado sin el filtrado](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en Internet Explorer, incluso si Internet Explorer no es su explorador predeterminado. En Skype para el negocio de la aplicación Web, un control ActiveX, un pequeño módulo que agrega características adicionales a una aplicación web o en otro programa, es necesario para audio, vídeo y uso compartido de la pantalla.
    
- Para algunas características de Skype para el negocio de la aplicación Web funcione correctamente, debe permitir su navegador para [guardar cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) en el equipo o dispositivo.
    
- Necesita para [Activar JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) se admitirán en el explorador para algunos Skype para funciones de negocio de la aplicación Web funcionar como se esperaba.
    
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos de cifrado debido a ASP .NET 4.5

A partir de Skype para Business Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede causar Skype App de reuniones no pueda iniciarse. Si un cliente está utilizando AES como el valor de la clave de validación de la máquina deberá restablecer el valor de la clave de la máquina a SHA-1 u otro algoritmo compatible en el nivel de sitio de reuniones de Skype la aplicación en IIS. Si es necesario, consulte [Administración de configuración de ASP.NET de IIS 8.0](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) .
  
Otros valores admitidos son:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 Los valores de MD5, 3DES y AES ya no pueden, como estaban una vez en ASP.NET 4. [Mejoras criptográficas en ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tiene más detalles.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

#### 

[Implementar a clientes de Web descargables en Skype para Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)
#### 

[Plataformas compatibles para la aplicación de las reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

