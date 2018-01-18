---
title: "Habilitar la difusión de la reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Antes de que las personas de su organización pueden utilizar Skype reunión difusión, debe habilitarlo. Para ello, necesita saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar a un socio de Microsoft para hacer este paso para usted."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar la difusión de la reunión de Skype

Antes de que las personas de su organización pueden utilizar Skype reunión difusión, debe habilitarlo. Para ello, necesita saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.
  
> [!CAUTION]
> Difusión de la reunión de Skype está desactivada de forma predeterminada porque la distribución del contenido multimedia de una reunión de difusión utiliza la red de entrega de contenido (CDN) de Microsoft Azure para lograr alta escala para soportar miles de personas viendo una difusión. Se cifra el contenido de medios fragmentada pasando por la CDN y la caché CDN tiene una vida limitada. Además, el componente Azure CDN puede todavía cumple con todos los elementos de las cláusulas del modelo de la UE derivados de la directiva de protección de datos de la Unión Europea. Al habilitar esta característica, usted reconoce este aviso. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Skype reunión difusión usando el Skype para el centro de administración de negocios

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. En el centro de administración de Office 365, vaya a **centros de Admin** > **Skype para el negocio**.
    
3. En el **Skype para el centro de administración de negocios**, vaya a **las reuniones en línea** > **reuniones de difusión**y, a continuación, seleccione **Habilitar la difusión de reunión de Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar Skype reunión difusión usando PowerShell

1. Compruebe que está ejecutando la versión 3.0 o posterior de Windows PowerShell.
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
2. En el **Menú Inicio**, elija **Windows PowerShell**.
    
3. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Confirme su configuración de Skype reunión difusión actual ejecutando:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Compruebe que el parámetro _EnableBroadcastMeeting_ está establecido en `False`.
    
     ![Cmdlet de Skype reunión difusión habilitar la organización.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Habilitar la difusión de reunión de Skype para su organización mediante la ejecución de:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Puede confirmar que la configuración está habilitada mediante la ejecución de `Get-CsBroadcastMeetingConfiguration` otra vez.
    
     ![Difusión de la reunión de Skype permiten Cmdlet de la organización.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Después de realizar el cambio, puede tardar hasta una hora surtan efecto en el portal de difusión de la reunión de Skype. 
  
6. Los usuarios ahora pueden contener difusión reuniones con otros usuarios de su negocio. Para obtenerlas iniciado, remítales a [¿Qué es una reunión de Skype difusión?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar la red para difundir reuniones con asistentes externos

Si tiene un firewall, y que desea que conserve las difusiones con personas fuera de su empresa (que no sean un negocio federado), debe configurar la red con estas instrucciones: [Configurar la red para difundir reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si no experimentados con la configuración del servidor de seguridad, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.
  
Para omitir este paso y en su lugar agregar otra empresa para la federación, vea [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Temas relacionados

[Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

