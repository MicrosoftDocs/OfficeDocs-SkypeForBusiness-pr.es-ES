---
title: Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación Web de Skype empresarial y la aplicación reuniones de Skype mientras planifica Skype empresarial Server. Este artículo no está destinado a los usuarios de estas aplicaciones.'
ms.openlocfilehash: f5b402b23cbb49d1605b83b9f54531e26714b1f7
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157643"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)
 
**Resumen:** Los profesionales de TI deben revisar los requisitos de soporte técnico para la aplicación Web de Skype empresarial y la aplicación reuniones de Skype mientras planifica Skype empresarial Server. Este artículo no está destinado a los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype empresarial Server, los usuarios de la organización tendrán en cuenta que el cliente de Skype empresarial se instalará como parte del proceso de implementación. 
  
Posteriormente, estos usuarios pueden crear reuniones e invitar a usuarios desde fuera de la organización, y las invitaciones a reuniones no pueden tener ninguna versión del cliente de Skype empresarial. Cuando los usuarios hagan clic en la dirección URL de la invitación a la reunión, se detectará la falta de un cliente y se le pedirá al invitado sin un cliente de Skype empresarial que descargue e instale un cliente ligero de solo reunión para que puedan unirse a la reunión.
  
> [!NOTE]
> La aplicación Web de Skype empresarial y la aplicación reuniones de Skype solo están disponibles cuando se intenta iniciar sesión en una reunión sin tener Skype empresarial. La ayuda para el usuario de estas [https://aka.ms/smahelp](https://aka.ms/smahelp)aplicaciones está en. 
  
> [!NOTE]
> No se puede preinstalar la aplicación Web de Skype empresarial o la aplicación reuniones de Skype, pero [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) y [tabletas](https://products.office.com/skype-for-business/download-app?tab=tabs-2) pueden instalar clientes móviles económicos que pueden usar para asistir a reuniones.
  
De forma predeterminada, el servidor que hospeda la reunión indicará al usuario que descargue e instale la aplicación Web de Skype empresarial para unirse a la reunión. La aplicación Web de Skype empresarial se almacena en el servidor front-end y se envía al asistente de la reunión. 
  
Para Skype empresarial Server, la aplicación reuniones de Skype (en Windows) y Skype empresarial para Mac (en Mac) están disponibles como reemplazos para la aplicación Web de Skype empresarial a partir de CU5, pero al ofrecer las aplicaciones de reemplazo se necesita la configuración adicional que se describe en [Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si la aplicación reuniones de Skype y Skype empresarial para Mac están habilitados, los usuarios descargarán la versión más reciente de las aplicaciones de la red de entrega de contenido (CDN) de Office 365 en lugar de hacerlo desde Skype empresarial Server. Para Skype empresarial Server 2019, usar la aplicación reuniones de Skype y Skype empresarial para Mac es la única opción.
  
La aplicación reuniones de Skype ofrece una experiencia de explorador simplificada para descargar e instalar la aplicación y unirse a reuniones, incluida la Unión con un solo clic para los usuarios de Internet Explorer. La aplicación reuniones de Skype también tiene muchas mejoras sobre la aplicación Web de Skype empresarial para la confiabilidad y la experiencia de reunión. 
  
> [!NOTE]
> A partir de Skype empresarial Server 2015 CU5 o versiones posteriores, las reuniones que se mantengan con Skype empresarial online ya no enviarán a un usuario sin cliente la aplicación Web de Skype empresarial, sino que, en su lugar, se les enviará la aplicación reuniones de Skype (en Windows) o Skype empresarial para Mac (en Mac). A partir de Skype empresarial Server 2015 CU5 o posterior, si [habilita la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), se enviará a los usuarios sin clientes la aplicación reuniones de Skype o Skype empresarial para Mac en lugar de la aplicación Web de Skype empresarial. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar la aplicación Web de Skype empresarial, un usuario debe tener una de las siguientes combinaciones de sistema operativo y explorador compatibles. 
  
**Sistema operativo y compatibilidad mínima con exploradores para la aplicación Web de Skype empresarial**

| Sistema operativo | Microsoft Edge | 32 para Internet Explorer 11 de 64 bits o posterior | 32 y 64 bits de Internet Explorer 10 o posterior | 32-y 64-bit Internet Explorer 9 o posterior | 32: versión de 64 bits de Safari 6.2.8-11. X | 32-y 64 bits de la versión de Chrome 18. X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|&#x2776; de Windows 8,1 <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sí &#x2778; <br/> |
|&#x2776; de Windows 8 (basado en Intel) <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D <br/> |N/D  <br/> |Sí &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |N/D <br/>|Sí &#x2778; <br/> |
|macOS 10,8 y versiones posteriores (basadas en Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí <br/> |
   
&#x2776; el complemento de explorador de la aplicación Web de Skype empresarial requiere un complemento de uso compartido específico para usar voz, vídeo, uso compartido y visualización del uso compartido de la pantalla continua y otras características en función del equipo. A un asistente a la reunión se le ofrece la opción de instalar el complemento para compartir, ya sea cuando se una a la reunión o cuando inicie una de estas características. En Windows 8 y Windows 8,1, el complemento para compartir solo puede instalarse si se está ejecutando Internet Explorer 10 o Internet Explorer 11 para el escritorio. Estas características no están disponibles con versiones que no son de escritorio de Internet Explorer 10 y 11. Tenga en cuenta que Firefox y Safari versión 12,0 y posteriores ya no se admiten.
  
&#x2777; en sistemas operativos compatibles con Windows 7, Windows Server 2008 R2 y Macintosh, todas las características están disponibles, incluidas la voz, vídeo, visualización de aplicaciones, uso compartido de aplicaciones, visualización de escritorio y uso compartido de escritorio basadas en el equipo. Para usar estas características, debe instalar un complemento cuando se le solicite. Tenga en cuenta que ya no se admite Mac OS X versión 10,7.  Tenga en cuenta también que la aplicación web no se instalará en OS X 10,15 o posterior.  Se recomienda usar la última versión de Skype empresarial para Mac, que admite escenarios de Unión anónima en el futuro.
  
&#x2778; el acceso a la aplicación web desde Chrome en Windows iniciará un pequeño programa que carga la aplicación web en un marco incrustado de Internet Explorer. Este programa requiere que esté instalada una de las versiones compatibles de Internet Explorer para que la aplicación web se cargue correctamente.
  
> [!NOTE]
> Office 365 los usuarios pueden usar Internet Explorer 10 o una versión posterior con Skype empresarial. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

La aplicación reuniones de Skype se ejecuta como una aplicación en equipos que usan Windows 10, Windows 8,1, Windows 8, Windows 7, con 32-y 64-bit Internet Explorer 11 o posterior instalado. 
  
Para cualquier otra dependencia, consulte [plataformas compatibles con la aplicación reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype Empresarial para Mac

Skype empresarial para Mac se ejecuta en equipos que usan macOS versión 10,8 o posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, auriculares con micrófono o dispositivos equivalentes compatibles con el equipo. Las características de vídeo requieren un dispositivo de vídeo compatible con el equipo. Para obtener información detallada sobre la compatibilidad de hardware de vídeo y la calidad de vídeo esperada, consulte [soluciones de vídeo del cliente de Skype](video-resolutions.md)empresarial.
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de Skype empresarial Web App o la aplicación reuniones de Skype experimenta problemas de conexión con la reunión, es probable que la infraestructura de red de su organización no esté configurada para admitir Office 365, tal como se describe en [office 365 URL e intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esto sucede tanto si la reunión fue creada por un usuario de Skype empresarial online o Skype empresarial Server. 
  
Si el usuario está en una red que no está configurada como se ha descrito, muchas características de la aplicación pueden funcionar o no y es posible que no puedan conectarse a la reunión.
  
## <a name="supported-meetings-features"></a>Características de las reuniones admitidas
<a name="BKMK_Conferencing"> </a>

En esta tabla se comparan las características de las reuniones disponibles para los usuarios del cliente de Skype empresarial, la aplicación Web de Skype empresarial, la aplicación reuniones de Skype y Lync Web App. Lync Web App se muestra con fines de comparación de características: un usuario solo descargaría y usar Lync Web App si la reunión se hospedaba en un servidor de Lync 2013.

| Característica/funcionalidad | Cliente de Skype empresarial 2016 o 2019 | Cliente de Skype empresarial en Mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Agregar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Cambiar el audio a un teléfono para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cambiar el audio a un teléfono para los participantes invitados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Ver vídeo entre varias partes (vista de galería)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Uso compartido de la pantalla basado en el vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (solo vista)  <br/> |||
|Usar controles de moderador de reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a lista de reuniones detallada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Establecer los mensajes INSTANTÁNEos como de importancia alta  <br/> |&#x2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |&#x2714; (requiere complemento)  <br/> |
|Compartir un programa (si se habilita)  <br/> |&#x2714;||&#x2714; (solo en Windows; requiere complemento)  <br/> |&#x2714; (solo en Windows; requiere complemento)  <br/> |&#x2714; (solo en Windows; requiere complemento)  <br/> |
|Tomar el control del programa o del escritorio compartido de otro usuario  <br/> |&#x2714;||&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |&#x2714; (&#x2776; solo en Windows; requiere complemento)  <br/> |
|Permitir que otro usuario tome el control del escritorio o programa compartidos  <br/> |&#x2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a los participantes por nombre  <br/> |&#x2714;|&#x2714;||||
|Invitar a participantes por número de teléfono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a participantes por correo electrónico  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniones de audio de acceso telefónico local  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar una reunión de reunirse ahora  <br/> |&#x2714;|&#x2714;||||
|Grabar una reunión  <br/> |&#x2714;|||||
|Agregar y descargar datos adjuntos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar por los archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar y editar notas de reunión de OneNote  <br/> |&#x2714;||Sólo Editar (no agregar)  <br/> |Sólo Editar (no agregar)  <br/> |Sólo Editar (no agregar)  <br/> |
|Usar una pizarra  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar sondeos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Cargar archivos para compartir con otros usuarios  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programar una conferencia o reunión  <br/> |Programador web de Outlook o Skype empresarial  <br/> |Programador web de Outlook o Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |Programador web de Skype empresarial  <br/> |
|T&amp;A Administrador  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Deshabilitar el vídeo del asistente  <br/> |&#x2714;|||||
|Deshabilitar la mensajería instantánea de reunión  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Silenciar a la audiencia  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convertir a todos en un asistente  <br/> |&#x2714;|||||
|Producir difusión de reunión de Skype  <br/> |&#x2714;|||||
   
 Los participantes de &#x2776; no pueden controlar los escritorios que comparten los usuarios de Skype empresarial para Mac, Lync para Mac 2011 o Communicator para Mac 2011. Esto tampoco funcionará para la aplicación Web de Skype empresarial en Max OSX.
  
 &#x2777; para Skype empresarial online, esta característica requiere conferencias RTC de Microsoft, mensajería unificada de Exchange o un proveedor de servicios de audioconferencia de terceros.
  
 &#x2778; el cliente de Lync para Mac 2011 no puede ver presentaciones de PowerPoint de Microsoft Office 2013 cuando se han compartido en una conferencia por la aplicación Web de Skype empresarial.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, la [ayuda en línea](https://aka.ms/smahelp) de estas aplicaciones está disponible fácilmente. Los profesionales de TI deben tener en cuenta los siguientes problemas:
  
- Si el usuario está en una red que no está configurada para cumplir los [requisitos de red](meetings-clients.md#Network), es posible que muchas características de la aplicación funcionen o no y que no puedan conectarse a la reunión.
    
- Algunos usuarios pueden tener equipos administrados por la empresa con permisos deshabilitados para instalar aplicaciones. para esos usuarios, ninguna aplicación es una opción, pero [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) y [tabletas](https://products.office.com/skype-for-business/download-app?tab=tabs-2) pueden instalar clientes móviles baratos que puedan usar para asistir a las reuniones.
    
    Otros problemas de instalación también se tratan en los [temas de ayuda](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Los usuarios pueden ver una advertencia de Firewall la primera vez que ejecutan la aplicación reuniones. Es posible que se les pida que abran los puertos para optimizar la experiencia y esto puede requerir privilegios de administrador en el equipo que no tengan. La aplicación debe seguir funcionando y el usuario puede rechazar de forma segura la apertura de los puertos solicitados. 
    
- ActiveX debe estar [habilitado sin filtrado](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en Internet Explorer, incluso si IE no es el explorador predeterminado. En la aplicación Web de Skype empresarial, un control ActiveX, un módulo pequeño que agrega características adicionales a una aplicación web o a otro programa, es necesario para el audio, vídeo y uso compartido de la pantalla.
    
- Para que algunas características de la aplicación Web de Skype empresarial funcionen correctamente, debe permitir que el explorador [Guarde las cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) en su equipo o dispositivo.
    
- Es posible que deba [Activar](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) la compatibilidad de JavaScript en el explorador para que algunas características de la aplicación Web de Skype empresarial funcionen del modo previsto.
    
### <a name="aes-support"></a>Compatibilidad con AES 

A partir de Skype empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4,6 y esto puede provocar que la aplicación reuniones de Skype no se inicie. [Los requisitos criptográficos para ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) tienen más detalles.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Implementar clientes Web descargables en Skype empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas compatibles con la aplicación reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
