---
title: "Configurar la red para Difusión de reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Configurar la red para Difusión de reunión de Skype

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f). 
  
Después de [Habilitar la Difusión de reunión de Skype](enable-skype-meeting-broadcast.md) Difusión de reunión de Skype, necesita configurar su red. Lleve a cabo este paso si quiere realizar seminarios web y demás difusiones para personas que no pertenecen a su empresa.
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y en su lugar agregar otra empresa para la federación, por lo que puede invitar a las emisiones, siga los pasos de [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Paso 1: Configurar los dominios permitidos

Use **uno** de los siguientes métodos para configurar dominios permitidos:
  
### 

 **Método 1: Usar el centro de administración de Office 365**
  
1. Vaya al **Centro de administración de Office 365** y, a continuación, en el panel de navegación izquierdo, haga clic en **configuración** > **servicios y complementos** y, a continuación, elija **Skype Empresarial**.
    
2. En la página de **uso compartido externo** en **excepciones de dominio**, seleccione **todos los dominios bloqueados excepto** y escriba los siguientes dominios, separados por una coma (,):
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Haga clic en **Guardar**.
    
### 

 **Método 2: Usar Windows PowerShell**
  
- En el **Menú Inicio**, haga clic en **Windows PowerShell** y haga clic en **Ejecutar como administrador**. En la ventana de **Windows PowerShell**, escriba cada línea y presione ENTRAR.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## Paso 2: Agregar dominios, la URL e IP de difusión de reunión de Skype direcciones

El segundo paso en el proceso de instalación es para que usted agregar dominios que son necesarios y, a continuación, agregue direcciones IP y URL necesarios para la difusión de reunión de Skype trabajar.
  
- **Agregue los extremos de dominio requerido:**
    
    Para usar la difusión de reuniones de Skype, los siguientes puntos de conexión deben estar accesibles para los equipos cliente.
    
|
|
|**Fila**|**Finalidad**|**Origen | Credenciales**|**Destino**|**ExpressRoute para Comunidades BGP de Office 365**|**Dirección CIDR**|**Puerto**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Necesario:** Puntos de conexión de Skype Empresarial. <br/> |vea [Skype Empresarial Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) y compruebe que todas las entradas con la etiqueta "Necesario" sean accesibles. <br/> ||||
|2  <br/> |**Necesario: moderador y asistente de**[Difusión de reunión de Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |equipo cliente/usuario con sesión iniciada  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|sí  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Necesario: moderador y asistente de**[Difusión de reunión de Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |equipo cliente/usuario con sesión iniciada  <br/> |
```
aka.ms
amp.azure.net

```

|no  <br/> |N/D  <br/> |TCP 443  <br/> |
|4  <br/> |**Necesario: moderador y asistente de**[Difusión de reunión de Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) (CDN incluidas) <br/> |equipo cliente/usuario con sesión iniciada  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|no  <br/> |N/D  <br/> |TCP 443  <br/> |
   
- **Agregar la requiere Skype empresarial Online direcciones URL de punto final y direcciones IP viendo cuáles son obligatorios**[aquí](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas

Si tiene una organización Skype Empresarial Online como una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype Empresarial Server 2015 y tiene usuarios tanto en línea y local, hay otros pasos de configuración que debe hacer además a las anteriores para habilitar su organización local para comunicarse con Skype Empresarial Online y permitir que todos los usuarios puedan crear y unirse a una Difusión de reunión de Skype. Para ver cuáles son los requisitos, vea [Configurar la implementación local de difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## Temas relacionados

[Habilitar la Difusión de reunión de Skype](enable-skype-meeting-broadcast.md)
  
[URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

