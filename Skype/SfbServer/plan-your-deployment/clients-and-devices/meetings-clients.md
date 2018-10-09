---
title: Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumen: Los profesionales de TI deben revisar los requisitos de soporte técnico para la Skype para la aplicación empresarial de Web y aplicación de las reuniones de Skype durante la planeación de Skype para Business Server. En este artículo no está pensada para los usuarios de estas aplicaciones.'
ms.openlocfilehash: c76770d570aaa1d1c686df7b0845e41a767cfbef
ms.sourcegitcommit: 80e1983fd631b8ad63c902375f1128faa957e374
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450637"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)
 
**Resumen:** LOS profesionales de TI deben revisar los requisitos de soporte técnico para la Skype para la aplicación empresarial de Web y aplicación de las reuniones de Skype durante la planeación de Skype para Business Server. En este artículo no está pensada para los usuarios de estas aplicaciones.
  
Una vez que haya implementado Skype para Business Server, los usuarios de su organización tendrán supuestamente el Skype para Business client instalado como parte del proceso de implementación. 
  
Más adelante en, esos usuarios pueden crear reuniones e invitar a los usuarios de fuera de la organización, y los invitados a la reunión no pueden tener cualquier versión de la Skype para clientes empresariales. Cuando los usuarios haga clic en la dirección URL de la invitación a la reunión, se detectará la falta de un cliente y el invitado sin un Skype para Business client le pedirá que descargue e instale a un cliente ligero, reuniones, por lo que puedan unirse a la reunión.
  
> [!NOTE]
> El Skype para la aplicación empresarial de Web y aplicación de las reuniones de Skype sólo están disponibles cuando intenta iniciar sesión en una reunión sin necesidad de Skype para la empresa. Ayuda de usuario para estas aplicaciones se encuentra en [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Pre-no se puede instalar cualquiera el Skype para la aplicación empresarial de Web o aplicación de las reuniones de Skype, pero los usuarios de [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y [tableta](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podrán instalar a económicos clientes móviles que puedan usar para asistir a reuniones.
  
De forma predeterminada, el servidor que hospeda la reunión dirige al usuario para descargar e instalar Skype para Business Web App para unirse a la reunión. El Skype para la aplicación empresarial de Web se almacena en el servidor Front-End y obtiene envían asistentes a la reunión. 
  
Para Skype para Business Server 2015, aplicación de las reuniones de Skype está disponible como un reemplazo de Skype para el principio de la aplicación Web de negocio con CU5, pero que proporciona la aplicación de las reuniones de Skype requiere la configuración adicional que se describen en [Habilitar la aplicación de las reuniones de Skype para reemplazar Skype para Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si está habilitada la aplicación de las reuniones de Skype, los usuarios descargarán la versión más reciente de la aplicación desde el Office 365 entrega red contenido (CDN), en lugar de su Skype para Business server. Para Skype para aplicaciones de negocio servidor 2019 Skype reuniones es la única opción.
  
Aplicación de las reuniones de Skype ofrece una experiencia de explorador simplificada para la descarga e instalación de la aplicación y unirse a reuniones, incluida la participación de un solo clic a los usuarios de Internet Explorer. Aplicación de las reuniones de Skype también tiene muchas mejoras a través de theSkype para la aplicación empresarial de Web para confiabilidad y la experiencia de reunión. 
  
> [!NOTE]
> A partir de Skype para Business Server 2015 CU5 o posterior, a las reuniones mediante Skype para profesionales en línea no volverá a enviar un usuario la Skype para la aplicación empresarial de Web, en su lugar se enviarán aplicación de las reuniones de Skype. A partir de Skype para Business Server 2015 CU5 o posterior, si se [Habilitar aplicación de las reuniones de Skype para reemplazar Skype para la aplicación empresarial de Web (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), los usuarios sin cliente se puede enviar aplicación de las reuniones de Skype en lugar de Skype para la aplicación empresarial de Web. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar el Skype para la aplicación empresarial de Web, un usuario debe haya uno de estos admite combinaciones de explorador y el sistema operativo. 
  
**Compatibilidad de explorador mínimo de Skype para la aplicación empresarial de Web y sistema operativo**

| Sistema operativo | Perimetral | Internet Explorer 11 o posterior de 32 y 64 bits | Internet Explorer 10 o una versión posterior de 32 y 64 bits | Internet Explorer 9 o posterior de 32 y 64 bits | Versión de 32 bits y de 64 bits de Safari 6.2.8 - 11.X | Versión de cromo de 32 y 64 bits 18.X o posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí & #x 2778; <br/> |
|Windows 8.1 & #x 2776; <br/> |N/D  <br/> |Sí  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sí & #x 2778; <br/> |
|Windows 8 (basado en Intel) & #x 2776; <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |N/D <br/> |N/D  <br/> |Sí & #x 2778; <br/> |
|Windows 7 con SP1 & #x 2777; <br/> |N/D  <br/> |Sí  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sí & #x 2778; <br/> |
|Windows Server 2008 R2 con SP1 & #x 2777; <br/> |N/D  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |N/D <br/>|Sí & #x 2778; <br/> |
|Mac OS 10,8 y versiones posteriores (basado en Intel) & #x 2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sí  <br/> |Sí <br/> |
   
& #x 2776; El Skype para el complemento de explorador Web App de negocio requiere un complemento del uso compartido específico para usar basados en un equipo de voz, vídeo, uso compartido y visualización de uso compartido de pantalla continuada y otras características. Asistente a una reunión se le da la opción para instalar el complemento de uso compartido cuando se unan a la reunión o cuando inicia una de estas características. En Windows 8 y Windows 8.1, el complemento de uso compartido puede instalarse sólo si se está ejecutando Internet Explorer 10 o Internet Explorer 11 para el escritorio. Estas características no se encuentran disponibles con la versión de Internet Explorer 10 o Internet Explorer 11 que no es de escritorio. Tenga en cuenta que ya no se admite Firefox y Safari versión 12.0 y versiones posterior.
  
& #x 2777; En compatibles Windows 7, Windows Server 2008 R2 y sistemas operativos Macintosh, todas las características están disponibles incluidos basados en un equipo de voz, vídeo, visualización de aplicaciones, uso compartido de aplicaciones, escritorio visualización y uso compartido de escritorio. Para usar estas características, necesita instalar un complemento cuando se le indique. No olvide que la versión 10.7 de Mac OS X ya no es compatible.
  
& #x 2778; Obtener acceso a la aplicación Web desde Chrome en Windows iniciará un pequeño programa que carga la aplicación Web en un marco de Internet Explorer incrustado. Este programa requiere la instalación de una de las versiones compatibles de Internet Explorer para que la aplicación web se cargue correctamente.
  
> [!NOTE]
> Los usuarios de Office 365 pueden utilizar Internet Explorer 10 o posterior con Skype para la empresa. 
  
### <a name="skype-meetings-app"></a>Aplicación Reuniones de Skype

La aplicación de las reuniones de Skype se ejecuta como una aplicación en equipos con Windows 10, Windows 8.1, Windows 8, Windows 7, con 32 y 64 bits Internet Explorer 11 o posterior instalado. 
  
La aplicación también ejecuta en Mac OS sistemas operativos 10.10 o posterior con ninguna dependencia del explorador específico. 
  
Para cualquier las dependencias, consulte [plataformas admitidas para la aplicación de las reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Los requisitos de hardware del equipo los determinan el sistema operativo y el explorador. Las características de voz y telefonía requieren un micrófono y altavoces, auriculares con micrófono o un dispositivo equivalente compatible con el equipo. Las características de vídeo necesitan un dispositivo de vídeo compatible con el equipo. Para obtener información detallada acerca de la compatibilidad de hardware de vídeo y la calidad de vídeo esperada, vea [Skype para resoluciones de vídeo de cliente empresarial](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de red
<a name="Network"> </a>

Si un usuario de Skype para experiencias de aplicación empresarial de Web o aplicación de las reuniones de Skype problemas de conexión de la reunión, lo más probable es la que infraestructura de red de su organización no está configurada para la compatibilidad con Office 365 tal como se describe en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Éste es el caso si la reunión se ha creado por un usuario de Skype para profesionales en línea o Skype para Business Server. 
  
Si el usuario está en una red que no está definida como se describe, es posible que muchas de las características de aplicación o puede que no funcione y es posible que no puedan conectarse a la reunión en absoluto.
  
## <a name="supported-meetings-features"></a>Características de reuniones compatibles
<a name="BKMK_Conferencing"> </a>

En esta tabla se compara las características de reuniones disponibles para los usuarios de Skype para clientes empresariales, Skype para la aplicación empresarial de Web, aplicación de las reuniones de Skype y Lync Web App. Lync Web App está en la lista para fines de comparación de características: un usuario sólo se debería descargar y usar Lync Web App si la reunión se hospeda en un servidor de Lync 2013.

| Característica / función | Skype para 2016 empresarial o cliente 2019 | Skype para la empresa en el cliente de Mac | Aplicación Reuniones de Skype | Aplicación web de Skype Empresarial | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar VoIP  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |
|Agregar vídeo  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |
|Cambiar el audio a un teléfono para los participantes autenticados  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Cambiar el audio a un teléfono para los participantes de invitado  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|||
|Ver un vídeo entre varios participantes (vista de galería)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Pantalla compartida basada en vídeo  <br/> |& #x 2714;|& #x 2714; <br/> |& #x2714;(View-only)  <br/> |||
|Usar los controles de moderador en la reunión  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Acceder a la lista de reuniones detallada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Establecer mensajes de mensajería instantánea como de importancia alta  <br/> |& #x 2714;|||||
|Compartir el escritorio (si se habilita)  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |& #x 2714; (requiere un complemento)  <br/> |
|Compartir un programa (si se habilita)  <br/> |& #x 2714;||& #x 2714; (en Windows solamente; requiere un complemento)  <br/> |& #x 2714; (en Windows solamente; requiere un complemento)  <br/> |& #x 2714; (en Windows solamente; requiere un complemento)  <br/> |
|Tomar el control del escritorio compartido o el programa de otro usuario  <br/> |& #x 2714;||& #x 2714; (& #x 2776; En Windows solamente; requiere un complemento)  <br/> |& #x 2714; (& #x 2776; En Windows solamente; requiere un complemento)  <br/> |& #x 2714; (& #x 2776; En Windows solamente; requiere un complemento)  <br/> |
|Permitir que otro usuario tome el control del escritorio compartido o programa  <br/> |& #x 2714;|||||
|Agregar participantes anónimos (si se habilita)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Invitar a participantes por su nombre  <br/> |& #x 2714;|& #x 2714;||||
|Invitar a participantes por número de teléfono  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Invitar a participantes por correo electrónico  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Usar reuniones de audio de acceso telefónico local  <br/> |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Empezar una reunión de tipo Reunirse ahora  <br/> |& #x 2714;|& #x 2714;||||
|Grabar una reunión  <br/> |& #x 2714;|||||
|Agregar y descargar los datos adjuntos  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Explorar archivos de Microsoft PowerPoint  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Agregar y editar las notas de reunión de OneNote  <br/> |& #x 2714;||Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |Solo editar (no agregar)  <br/> |
|Usar una pizarra  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Realizar sondeos  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Cargar archivos para compartirlos con otros usuarios  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Programar una reunión o conferencia  <br/> |Outlook o Skype para el programador Web empresarial  <br/> |Outlook o Skype para el programador Web empresarial  <br/> |Skype para el programador Web empresarial  <br/> |Skype para el programador Web empresarial  <br/> |Skype para el programador Web empresarial  <br/> |
|Q&amp;un administrador  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Deshabilitar el vídeo de asistentes  <br/> |& #x 2714;|||||
|Deshabilitar la mensajería instantánea de la reunión  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Silenciar destinatarios  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Convertir a todos en asistentes  <br/> |& #x 2714;|||||
|Producir difusión de reunión de Skype  <br/> |& #x 2714;|||||
   
 & #x 2776;  Los participantes no pueden controlar los escritorios compartidos por Skype para la empresa para Mac, Lync para Mac 2011 o Communicator para Mac 2011 a los usuarios. Esto tampoco funcionará con la aplicación web de Skype Empresarial en Mac OS X.
  
 & #x 2777;  Para Skype para profesionales en línea, esta característica requiere Microsoft RTC conferencia, mensajería unificada de Exchange, o un 3 º proveedor de conferencias de audio.
  
 & #x 2778;  El Lync para Mac 2011 cliente no puede ver las presentaciones de PowerPoint de Microsoft Office 2013 cuando que han sido compartidas en una conferencia por la Skype para la aplicación empresarial de Web.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conocidos y solución de problemas
<a name="BKMK_Conferencing"> </a>

Para los usuarios finales, está disponible la [Ayuda en pantalla](https://aka.ms/smahelp) para estas aplicaciones. LOS profesionales de TI deben tener en cuenta los siguientes problemas:
  
- Si el usuario está en una red no configurado para cumplir los [requisitos de red](meetings-clients.md#Network), muchas características de la aplicación pueden o no funcionen y es posible que no puedan conectarse a la reunión en todos los.
    
- Algunos usuarios pueden tener corporativo administra equipos con permiso deshabilitado para instalar aplicaciones. para aquellos usuarios ni aplicación es una opción, pero los usuarios de [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) y [tableta](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podrán instalar a económicos clientes móviles que puedan usar para asistir a reuniones.
    
    Otros problemas de instalación también se tratan en los [temas de ayuda](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Los usuarios pueden ver un firewall advertencia la primera vez ejecuten la aplicación de las reuniones. Es posible que se le pida abrir puertos para optimizar la experiencia de y es posible que tenga privilegios de administrador en el equipo que no es posible que tengan. Aún debería funcionar de la aplicación y el usuario puede rechazar de forma segura abrir los puertos solicitados. 
    
- Debe tener [ActiveX habilitado sin el filtrado](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) en el Explorador de Internet, incluso si Internet Explorer no es su explorador predeterminado. En Skype para la aplicación empresarial de Web, un control ActiveX: un módulo pequeño que agrega funciones adicionales a una aplicación web o de otro programa, es necesario para audio, vídeo y uso compartido de la pantalla.
    
- Para algunas características de Skype para la aplicación empresarial de Web para que funcione correctamente, debe permitir que el explorador para [Guardar las cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) en su equipo o dispositivo.
    
- Es posible que necesite para [Activar JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) admita en su explorador para algunos Skype para las características de aplicación Web de negocio para que funcione como se esperaba.
    
### <a name="aes-support"></a>Soporte técnico AES 

A partir de Skype para Business Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede causar la aplicación de las reuniones de Skype que se inicie. [Requisitos de cifrado debido a ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) tiene más detalles.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Implementar a los clientes que se pueden descargar de Web en Skype para Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para la aplicación de las reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
