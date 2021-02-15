---
title: Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)
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
description: 'Resumen: los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación web de Skype Empresarial y la aplicación reuniones de Skype mientras planean Skype Empresarial Server. Este artículo no está pensado para los usuarios de estas aplicaciones.'
ms.openlocfilehash: 4956a11c0ed163cbe50c49233e9aa05a0fbbd872
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826020"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)
 
**Resumen:** Los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación web de Skype Empresarial y la aplicación reuniones de Skype mientras planean Skype Empresarial Server. Este artículo no está pensado para los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype Empresarial Server, los usuarios de su organización presumiblemente tendrán instalado el cliente de Skype Empresarial como parte del proceso de implementación. 
  
Más adelante, esos usuarios pueden crear reuniones e invitar a usuarios de fuera de la organización, y es posible que los invitados a la reunión no tengan ninguna versión del cliente de Skype Empresarial. Cuando esos usuarios hacen clic en la dirección URL de la invitación a la reunión, se detectará la falta de un cliente y se pedirá al invitado que no tenga un cliente de Skype Empresarial que descargue e instale un cliente ligero de solo reuniones para que pueda unirse a la reunión.
  
> [!NOTE]
> La aplicación web de Skype Empresarial y la aplicación Reuniones de Skype solo están disponibles al intentar iniciar sesión en una reunión sin tener Skype Empresarial. La ayuda del usuario para estas aplicaciones se encuentra en [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> You can't pre-install either the Skype for Business Web App or Skype Meetings App, but [smart phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) and [tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) users may be able to install económico mobile clients they can use to attend meetings.
  
De forma predeterminada, el servidor que hospeda la reunión dirigirá al usuario a descargar e instalar Skype Empresarial Web App para unirse a la reunión. La aplicación web de Skype Empresarial se almacena en el servidor front-end y se envía al asistente a la reunión. 
  
For Skype for Business Server, Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac) are available as replacements for Skype for Business Web App beginning with CU5, but providing the replacement apps requires the additional configuration described in [Enable Skype Meetings App to replace Skype for Business Web App (Optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Si la aplicación Reuniones de Skype y Skype Empresarial para Mac están habilitadas, los usuarios descargarán la versión más reciente de las aplicaciones desde la red de entrega de contenido (CDN) de Microsoft 365 u Office 365, en lugar de desde su servidor de Skype Empresarial. Para Skype Empresarial Server 2019, la única opción es usar la aplicación Reuniones de Skype y Skype Empresarial para Mac.
  
La aplicación Reuniones de Skype ofrece una experiencia de explorador simplificada para descargar e instalar la aplicación y unirse a reuniones, incluida la unión con un solo clic para los usuarios de Internet Explorer. La aplicación reuniones de Skype también tiene muchas mejoras sobre la aplicación web de Skype Empresarial para la confiabilidad y la experiencia de la reunión. 
  
> [!NOTE]
> A partir de Skype Empresarial Server 2015 CU5 o posterior, las reuniones realizadas con Skype Empresarial Online ya no enviarán a un usuario sin cliente la aplicación web de Skype Empresarial, sino que se les enviará la aplicación Reuniones de Skype (en Windows) o Skype Empresarial para Mac (en Mac). A partir de Skype Empresarial Server 2015 CU5 o posterior, si habilita la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial [(opcional),](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)los usuarios sin cliente recibirán la aplicación Reuniones de Skype o Skype Empresarial para Mac en lugar de la aplicación web de Skype Empresarial. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar la aplicación web de Skype Empresarial, un usuario debe tener una de las siguientes combinaciones de sistema operativo y explorador compatibles. 
  
**Sistema operativo y compatibilidad mínima con exploradores para Skype Empresarial Web App**

| Sistema operativo | Microsoft Edge | Internet Explorer 11 o posterior de 32 y 64 bits | Internet Explorer 10 o posterior de 32 y 64 bits | Internet Explorer 9 o posterior de 32 y 64 bits | Versión de 32 y 64 bits de Safari 6.2.8 - 11.X | Versión de 32 y 64 bits de Chrome 18.X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sí &#x2778; <br/> |
|Windows 8 (basado en Intel) &#x2776; <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|macOS 10.8 y versiones posteriores (basados en Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí <br/> |
   
&#x2776; complemento de explorador de Skype Empresarial Web App requiere un complemento de uso compartido específico para usar voz, vídeo, uso compartido y visualización de pantalla compartida continua y otras características. Un asistente a la reunión tiene la opción de instalar el complemento de uso compartido cuando se une a la reunión o cuando inicia una de estas características. En Windows 8 y Windows 8.1, el complemento para compartir solo se puede instalar si ejecutas Internet Explorer 10 o Internet Explorer 11 para el escritorio. Estas características no están disponibles con versiones que no son de escritorio de Internet Explorer 10 y 11. Tenga en cuenta que Firefox y Safari versión 12.0 y versiones posteriores ya no son compatibles.
  
&#x2777; En los sistemas operativos Compatibles con Windows 7, Windows Server 2008 R2 y Macintosh, todas las características están disponibles, como voz basada en equipo, vídeo, visualización de aplicaciones, uso compartido de aplicaciones, visualización de escritorio y uso compartido de escritorio. Para usar estas características, debe instalar un complemento cuando se le solicite. Ten en cuenta que ya no se admite Mac OS X versión 10.7.  Tenga en cuenta también que la aplicación web no se instalará en OS X 10.15 o posterior.  Se recomienda usar la versión más reciente de Skype Empresarial para Mac, que admite escenarios de unión anónima en el futuro.
  
&#x2778; obtener acceso a la aplicación web desde Chrome en Windows se iniciará un pequeño programa que carga la aplicación web en un marco de Internet Explorer incrustado. Este programa requiere que una de las versiones compatibles de Internet Explorer esté instalada para que la aplicación web se cargue correctamente.
  
> [!NOTE]
> Los usuarios de Microsoft 365 y Office 365 pueden usar Internet Explorer 10 o posterior con Skype Empresarial. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

La aplicación Reuniones de Skype se ejecuta como una aplicación en equipos con Windows 10, Windows 8.1, Windows 8, Windows 7, con Internet Explorer 11 de 32 y 64 bits o posterior instalado. 
  
Para cualquier otra dependencia, consulte [Plataformas admitidas para la aplicación Reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype Empresarial para Mac

Skype Empresarial para Mac se ejecuta en equipos con macOS versión 10.8 o posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, unos auriculares con micrófono o un dispositivo equivalente compatible con el equipo. Las características de vídeo requieren un dispositivo de vídeo compatible con el equipo. Para obtener información detallada sobre la compatibilidad con hardware de vídeo y la calidad de vídeo esperada, vea resoluciones de vídeo del [cliente de Skype Empresarial.](video-resolutions.md)
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de Skype Empresarial Web App o de la aplicación Reuniones de Skype experimenta problemas de conexión de reuniones, lo más probable es que la infraestructura de red de su organización no esté configurada para admitir Office 365 como se describe en las direcciones URL de [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)y los intervalos de direcciones IP. Este es el caso si la reunión fue creada por un usuario de Skype Empresarial Online o Skype Empresarial Server. 
  
Si el usuario está en una red no configurada como se describe, muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión.
  
## <a name="supported-meetings-features"></a>Características de reuniones admitidas
<a name="BKMK_Conferencing"> </a>

En esta tabla se comparan las características de reuniones disponibles para los usuarios del cliente de Skype Empresarial, la aplicación web de Skype Empresarial, la aplicación reuniones de Skype y Lync Web App. Lync Web App se muestra con fines de comparación de características: un usuario solo descargaría y usaría Lync Web App si la reunión se hospedase en un servidor de Lync 2013.

| Característica/funcionalidad | Cliente de Skype Empresarial 2016 o 2019 | Cliente de Skype Empresarial en Mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Agregar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Cambiar el audio a un teléfono para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cambiar el audio a un teléfono para los participantes invitados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Ver vídeo entre varias entidades (vista galería)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Uso compartido de la pantalla basado en el vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(solo vista)  <br/> |||
|Usar controles de moderador de reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a lista de reuniones detallada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Establecer mensajes de mensajería instantánea como de importancia alta  <br/> |&#x2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Compartir un programa (si se habilita)  <br/> |&#x2714;||&#x2714;(Solo en Windows; requiere complemento)  <br/> |&#x2714;(Solo en Windows; requiere complemento)  <br/> |&#x2714;(Solo en Windows; requiere complemento)  <br/> |
|Tomar el control del escritorio o programa compartido de otro usuario  <br/> |&#x2714;||&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |
|Permitir que otro usuario controle el escritorio o programa compartido  <br/> |&#x2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por nombre  <br/> |&#x2714;|&#x2714;||||
|Invitar a participantes por número de teléfono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por correo electrónico  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniones de audio de acceso telefónico  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar una reunión reunirse ahora  <br/> |&#x2714;|&#x2714;||||
|Grabar una reunión  <br/> |&#x2714;|||||
|Agregar y descargar datos adjuntos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar por archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar y editar notas de reunión de OneNote  <br/> |&#x2714;||Solo edición (no agregar)  <br/> |Solo edición (no agregar)  <br/> |Solo edición (no agregar)  <br/> |
|Usar una pizarra  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar sondeos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Cargar archivos para compartirlos con otros usuarios  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programar una conferencia o reunión  <br/> |Programador web de Outlook o Skype Empresarial  <br/> |Programador web de Outlook o Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |Programador web de Skype Empresarial  <br/> |
|Administrador &amp; de preguntas y respuestas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Deshabilitar vídeo de asistente  <br/> |&#x2714;|||||
|Deshabilitar mensajería instantánea de reunión  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Silenciar audiencia  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convertir a todos en asistentes  <br/> |&#x2714;|||||
|Producir Difusión de reunión de Skype  <br/> |&#x2714;|||||
   
 &#x2776; participantes no pueden controlar los escritorios que comparten los usuarios de Skype Empresarial para Mac, Lync para Mac 2011 o Communicator para Mac 2011. Esto tampoco funcionará para Skype Empresarial Web App en Max OSX.
  
 &#x2777; Skype Empresarial Online, esta característica requiere conferencias RTC de Microsoft, mensajería unificada de Exchange o un proveedor de audioconferencia de terceros.
  
 &#x2778; el cliente de Lync para Mac 2011 no puede ver presentaciones de PowerPoint de Microsoft Office 2013 cuando la aplicación web de Skype Empresarial las ha compartido en una conferencia.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, la [ayuda en línea](https://aka.ms/smahelp) para estas aplicaciones está disponible fácilmente. Los profesionales de IT deben tener en cuenta los siguientes problemas:
  
- Si el usuario está en una red no configurada para cumplir los requisitos de [red,](meetings-clients.md#Network)muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión.
    
- Algunos usuarios pueden tener equipos administrados por la empresa con permiso deshabilitado para instalar aplicaciones. para esos usuarios, ninguna aplicación [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) es una opción, pero los usuarios de teléfonos inteligentes y [tabletas](https://products.office.com/skype-for-business/download-app?tab=tabs-2) pueden instalar clientes móviles económicos que pueden usar para asistir a reuniones.
    
    En los temas de ayuda también se tratan otros problemas [de instalación.](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US) 
    
- Los usuarios pueden ver una advertencia de firewall la primera vez que ejecutan la aplicación de reuniones. Es posible que se les pida que abran puertos para optimizar la experiencia, lo que puede requerir privilegios de administrador en el equipo que no tengan. La aplicación debe seguir funcionando y el usuario puede rechazar de forma segura abrir los puertos solicitados. 
    
- Debes tener ActiveX [sin filtrar](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en Internet Explorer, incluso si IE no es el explorador predeterminado. En Skype Empresarial Web App, se necesita un control de ActiveX (un pequeño módulo que agrega características adicionales a una aplicación web u otro programa) para el uso compartido de audio, vídeo y pantalla.
    
- Para que algunas características de Skype Empresarial Web App funcionen correctamente, debe permitir que el explorador guarde [cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) en su equipo o dispositivo.
    
- Es posible que tenga [que activar la compatibilidad con JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) en el explorador para que algunas características de Skype Empresarial Web App funcionen según lo esperado.
    
### <a name="aes-support"></a>Soporte técnico de AES 

A partir de Skype Empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede provocar que la aplicación Reuniones de Skype no se inicie. [Los requisitos criptográficos debido a ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) tienen más detalles.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Implementar clientes web descargables en Skype Empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para la aplicación Reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
