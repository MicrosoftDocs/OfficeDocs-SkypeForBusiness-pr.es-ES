---
title: Plan for Meetings clients (Web App and Meetings App)
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumen: los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación aplicación web de Skype Empresarial y Skype reuniones mientras planean Skype Empresarial Server. Este artículo no está pensado para los usuarios de estas aplicaciones.'
ms.openlocfilehash: 575b1c7a5d335350ade6008cd0713b89b7e14ad07e86f290c98b72fcfdcd7cd4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281703"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Plan for Meetings clients (Web App and Meetings App)
 
**Resumen:** Los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación aplicación web de Skype Empresarial y Skype reuniones mientras planean Skype Empresarial Server. Este artículo no está pensado para los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype Empresarial Server, los usuarios de la organización presumiblemente tendrán el cliente de Skype Empresarial instalado como parte del proceso de implementación. 
  
Más adelante, esos usuarios pueden crear reuniones e invitar a usuarios de fuera de la organización, y es posible que los invitados a la reunión no tengan ninguna versión del Skype Empresarial cliente. Cuando esos usuarios hacen clic en la dirección URL de la invitación a la reunión, se detectará la falta de un cliente y se pedirá al invitado que no tenga un cliente de Skype Empresarial que descargue e instale un cliente ligero de solo reuniones para que pueda unirse a la reunión.
  
> [!NOTE]
> La aplicación web de Skype Empresarial y Skype reuniones solo están disponibles al intentar iniciar sesión en una reunión sin tener Skype Empresarial. La ayuda del usuario para estas aplicaciones se encuentra en [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> No puede preinstalar la aplicación de reuniones de aplicación web de Skype Empresarial o Skype, [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) pero [](https://products.office.com/skype-for-business/download-app?tab=tabs-2) los usuarios de teléfonos inteligentes y tabletas pueden instalar clientes móviles económicos que pueden usar para asistir a reuniones.
  
De forma predeterminada, el servidor que hospeda la reunión dirigirá al usuario a descargar e instalar aplicación web de Skype Empresarial para unirse a la reunión. El aplicación web de Skype Empresarial se almacena en el servidor front-end y se envía al asistente a la reunión. 
  
Por Skype Empresarial Server, Skype Meetings App (en Windows) y Skype Empresarial para Mac (en Mac) están disponibles como reemplazos para aplicación web de Skype Empresarial empezando por CU5, pero proporcionar las aplicaciones de reemplazo requiere la configuración adicional descrita en [Enable Skype Meetings App to replace aplicación web de Skype Empresarial (Optional).](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable) Si Skype Meetings App y Skype Empresarial para Mac están habilitados, los usuarios descargarán la versión más reciente de las aplicaciones desde Microsoft 365 o Office 365 Content Delivery Network (CDN) en lugar de desde el servidor Skype Empresarial. Para Skype Empresarial Server 2019, usar Skype meetings app y Skype Empresarial para Mac es la única opción.
  
Skype Meetings App ofrece una experiencia de explorador simplificada para descargar e instalar la aplicación y unirse a reuniones, incluido unirse con un solo clic para los usuarios de Internet Explorer. Skype Meetings App también tiene muchas mejoras sobre el aplicación web de Skype Empresarial para la confiabilidad y la experiencia de la reunión. 
  
> [!NOTE]
> A partir de Skype Empresarial Server 2015 CU5 o posterior, las reuniones celebradas con Skype Empresarial Online ya no enviarán a un usuario sin cliente el aplicación web de Skype Empresarial, sino que se enviarán Skype Meetings App (en Windows) o Skype Empresarial para Mac (en Mac). A partir de Skype Empresarial Server 2015 CU5 o posterior, si habilita Skype Meetings App para reemplazar [aplicación web de Skype Empresarial (opcional),](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)los usuarios sin cliente se enviarán Skype Meetings App o Skype Empresarial para Mac en lugar de aplicación web de Skype Empresarial. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar el aplicación web de Skype Empresarial, un usuario debe tener una de las siguientes combinaciones de sistema operativo y explorador compatibles. 
  
**Sistema operativo y compatibilidad mínima con exploradores para aplicación web de Skype Empresarial**

| Sistema operativo | Microsoft Edge | Internet Explorer 11 o posterior de 32 y 64 bits | 32 y 64 bits Internet Explorer 10 o posterior | Internet Explorer 9 o posterior de 32 y 64 bits | Versión de 32 y 64 bits de Safari 6.2.8 - 11.X | Versión de 32 y 64 bits de Chrome 18.X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sí &#x2778; <br/> |
|Windows 8 (basado en Intel) &#x2776; <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|Windows Servidor 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|macOS 10.8 y versiones posteriores (basados en Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí <br/> |
   
&#x2776; El complemento aplicación web de Skype Empresarial explorador de aplicación web de Skype Empresarial requiere un complemento de uso compartido específico para usar la voz, el vídeo, el uso compartido y la visualización de pantalla compartida continua y otras características. A los asistentes a la reunión se les ofrece la opción de instalar el complemento de uso compartido cuando se unen a la reunión o cuando inician una de estas características. En Windows 8 y Windows 8.1, el complemento de uso compartido solo se puede instalar si está ejecutando Internet Explorer 10 o Internet Explorer 11 para el escritorio. Estas características no están disponibles con versiones que no son de escritorio de Internet Explorer 10 y 11. Ten en cuenta que Firefox y Safari versión 12.0 y versiones posteriores ya no son compatibles.
  
&#x2777; On supported Windows 7, Windows Server 2008 R2, and Macintosh operating systems, all features are available including computer-based voice, video, application viewing, application sharing, desktop viewing, and desktop sharing. Para usar estas características, debe instalar un complemento cuando se le pida. Tenga en cuenta que Mac OS X versión 10.7 ya no es compatible.  Ten en cuenta también que la aplicación web no se instalará en OS X 10.15 o posterior.  Se recomienda usar la versión más reciente de Skype Empresarial para Mac que admita escenarios de unión anónimos avanzando.
  
&#x2778; El acceso a la aplicación web desde Chrome en Windows iniciará un pequeño programa que carga la aplicación web en un marco incrustado de Internet Explorer. Este programa requiere que se instale una de las versiones compatibles de Internet Explorer para que la aplicación web se cargue correctamente.
  
> [!NOTE]
> Microsoft 365 y Office 365 usuarios pueden usar Internet Explorer 10 o posterior con Skype Empresarial. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

Skype Meetings App se ejecuta como una aplicación en equipos que usan Windows 10, Windows 8.1, Windows 8, Windows 7, con Internet Explorer 11 o posterior de 32 y 64 bits instalado. 
  
Para otras dependencias, consulte [Plataformas admitidas para Skype Meetings App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype Empresarial para Mac

Skype Empresarial para Mac se ejecuta en equipos con macOS versión 10.8 o posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, auriculares con micrófono o dispositivo equivalente compatible con el equipo. Las características de vídeo requieren un dispositivo de vídeo compatible con el equipo. Para obtener información detallada sobre el soporte de hardware de vídeo y la calidad de vídeo esperada, vea [Skype Empresarial de vídeo de cliente.](video-resolutions.md)
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de aplicación web de Skype Empresarial o de Skype Meetings App experimenta problemas de conexión de reuniones, lo más probable es que la infraestructura de red de su organización no esté configurada para admitir Office 365 como se describe en Office 365 URL e [intervalos](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)de direcciones IP . Este es el caso de si la reunión fue creada por un usuario de Skype Empresarial Online o Skype Empresarial Server. 
  
Si el usuario está en una red no configurada como se describe, muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión en absoluto.
  
## <a name="supported-meetings-features"></a>Características de reuniones admitidas
<a name="BKMK_Conferencing"> </a>

En esta tabla se comparan las características de reuniones disponibles para los usuarios del cliente de Skype Empresarial, aplicación web de Skype Empresarial, Skype Meetings App y Lync Web App. Lync Web App aparece con fines de comparación de características: un usuario solo estaría descargando y usando Lync Web App si la reunión se hospedase en un servidor de Lync 2013.

| Característica/funcionalidad | Skype Empresarial 2016 o 2019 | Skype Empresarial cliente mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Agregar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Cambiar el audio a un teléfono para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cambiar el audio a un teléfono para los participantes invitados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Ver vídeo multiparte (vista galería)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Uso compartido de la pantalla basado en el vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(solo vista)  <br/> |||
|Usar controles de moderador de reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a lista de reuniones detallada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Establecer mensajes de mensajería instantánea como de gran importancia  <br/> |&#x2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Compartir un programa (si se habilita)  <br/> |&#x2714;||&#x2714;(On Windows solo; requiere un complemento)  <br/> |&#x2714;(On Windows solo; requiere un complemento)  <br/> |&#x2714;(On Windows solo; requiere un complemento)  <br/> |
|Tomar el control del programa o escritorio compartido de otro usuario  <br/> |&#x2714;||&#x2714; (&#x2776; Solo Windows, requiere complemento)  <br/> |&#x2714; (&#x2776; Solo Windows, requiere complemento)  <br/> |&#x2714; (&#x2776; Solo Windows, requiere complemento)  <br/> |
|Permitir que otro usuario tome el control de su programa o escritorio compartido  <br/> |&#x2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por su nombre  <br/> |&#x2714;|&#x2714;||||
|Invitar a los participantes por número de teléfono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por correo electrónico  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniones de audio de acceso telefónico  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar una reunión de Meet Now  <br/> |&#x2714;|&#x2714;||||
|Grabar una reunión  <br/> |&#x2714;|||||
|Agregar y descargar datos adjuntos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar por archivos PowerPoint Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar y editar notas OneNote reunión  <br/> |&#x2714;||Solo edición (no agregar)  <br/> |Solo edición (no agregar)  <br/> |Solo edición (no agregar)  <br/> |
|Usar una pizarra  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar sondeos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Upload archivos para compartir con otros usuarios  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programar una conferencia o reunión  <br/> |Outlook o Programador web de Skype Empresarial  <br/> |Outlook o Programador web de Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |
|Q &amp; A Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Deshabilitar vídeo de asistente  <br/> |&#x2714;|||||
|Deshabilitar la mensajería instantánea de reunión  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Silenciar audiencia  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convertir a todos en asistentes  <br/> |&#x2714;|||||
|Producir Skype difusión de reunión  <br/> |&#x2714;|||||
   
 &#x2776; Los participantes no pueden controlar escritorios compartidos por Skype Empresarial para Mac, Lync para Mac 2011 o Communicator usuarios de Mac 2011. Esto tampoco funcionará para aplicación web de Skype Empresarial max OSX.
  
 &#x2777; Para Skype Empresarial Online, esta característica requiere conferencia RTC de Microsoft, Exchange mensajería unificada o un proveedor de audioconferencia de terceros.
  
 &#x2778; El cliente de Lync para Mac 2011 no puede ver Microsoft Office presentaciones de PowerPoint de 2013 cuando el aplicación web de Skype Empresarial las ha compartido en una aplicación web de Skype Empresarial.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, la [ayuda en línea](https://aka.ms/smahelp) para estas aplicaciones está disponible fácilmente. Los profesionales de IT deben ser conscientes de los siguientes problemas:
  
- Si el usuario está en una red que no está configurada para cumplir los requisitos de [red,](meetings-clients.md#Network)muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión en absoluto.
    
- Algunos usuarios pueden tener equipos administrados por la empresa con permiso deshabilitado para instalar aplicaciones. para esos usuarios, ninguna aplicación [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) es una [](https://products.office.com/skype-for-business/download-app?tab=tabs-2) opción, pero los usuarios de teléfonos inteligentes y tabletas pueden instalar clientes móviles económicos que pueden usar para asistir a reuniones.
    
    Otros problemas de instalación también se tratan en los [temas de ayuda](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Los usuarios pueden ver una advertencia de firewall la primera vez que ejecutan la aplicación de reuniones. Es posible que se les pida que abran puertos para optimizar la experiencia, lo que puede requerir privilegios de administrador en la máquina que quizás no tengan. La aplicación debe seguir funcionando y el usuario puede rechazar de forma segura abrir los puertos solicitados. 
    
- Debe haber habilitado [ActiveX sin filtrar](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en Internet Explorer, incluso si IE no es su explorador predeterminado. En aplicación web de Skype Empresarial, se requiere un control ActiveX , un pequeño módulo que agrega características adicionales a una aplicación web u otro programa, para compartir audio, vídeo y pantalla.
    
- Para que algunas características aplicación web de Skype Empresarial funcionen correctamente, debes permitir que el explorador guarde [cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) en el equipo o dispositivo.
    
- Es posible que deba [activar la compatibilidad con JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) en el explorador para que aplicación web de Skype Empresarial características funcionen según lo esperado.
    
### <a name="aes-support"></a>Compatibilidad con AES 

A partir de Skype Empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede provocar que Skype Meetings App no se inicie. [Los requisitos criptográficos ASP.NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) tienen más detalles.
  
## <a name="see-also"></a>Consulte también
<a name="BKMK_Conferencing"> </a>

[Implementar clientes descargables web en Skype Empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para Skype Meetings App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
