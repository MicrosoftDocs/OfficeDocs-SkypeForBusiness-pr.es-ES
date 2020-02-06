---
title: Planear la experiencia del cliente de Skype empresarial 2015 para los usuarios
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumen: Obtenga información sobre el nuevo Skype empresarial y los pasos que puede realizar para preparar su entorno y sus usuarios para la actualización, ya sea que esté usando Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015, Lync Server 2013 o Lync Server 2010.'
ms.openlocfilehash: afd0f9f8a764ef9430d9ac1a9887a872c02fedd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803530"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planear la experiencia del cliente de Skype empresarial 2015 para los usuarios
 
**Resumen:** Obtenga más información sobre el nuevo Skype empresarial y los pasos que puede realizar para preparar su entorno y sus usuarios para la actualización, ya sea que esté usando Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015, Lync Server 2013 o Lync Server 2010.
  
El 14 de abril de 2015 Office Update para Lync 2013 incluye la nueva interfaz de usuario de Skype empresarial. Esta actualización permite a los administradores controlar la apariencia del cliente y elegir si desea conservar la experiencia del cliente de Lync 2013 o usar la experiencia mejorada de cliente de Skype empresarial. El cliente de Skype empresarial ha reemplazado de manera efectiva el cliente de Lync 2013 y ha agregado la posibilidad de que los administradores elijan entre la experiencia del cliente de Lync existente y la nueva experiencia de cliente de Skype empresarial. Para obtener más información sobre esta actualización, consulte [actualización del 14 de abril de 2015 para Lync 2013 (Skype empresarial) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
El 12 de mayo de 2015, habrá otra actualización mensual de Office que incluya el cliente de Skype empresarial actualizado. Muchos clientes que no aplican la actualización de abril recibirán la actualización de mayo de 12 para Office 2013. La información de este tema le ayudará a preparar a su organización, el entorno y sus usuarios para la actualización del cliente. Para que la transición sea fácil para los usuarios y equipos de asistencia, use la información de este tema como ayuda para decidir qué experiencia de cliente desea para los usuarios y, a continuación, realice los cambios en el entorno antes de implementar la actualización del cliente en la organización.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el cliente de Skype Empresarial](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para sus usuarios?
<a name="clientexperience"> </a>

Con el nuevo cliente de Skype empresarial, puede controlar qué experiencia de cliente obtienen sus usuarios, ya sea Lync o Skype empresarial. La experiencia de cliente predeterminada depende de si usa Lync o Skype empresarial local o en línea. Si está usando Skype empresarial online (Lync Online) hoy mismo con Office 365 ProPlus, Office 365 Business Premium u Office 2013, la experiencia de cliente actualizada de Skype empresarial, inspirada en el aspecto de Skype, será la experiencia de usuario predeterminada. Si usa Lync Server local hoy mismo, la experiencia del cliente de Lync será la predeterminada.
  
Puede configurar la experiencia de cliente que obtienen los usuarios mediante las directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando inician sesión en Lync o Skype empresarial.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype Empresarial

Además de todas las características de Lync, Skype empresarial ofrece nuevas características con controles simplificados y iconos familiares de Skype. Algunas características nuevas de Skype empresarial solo están disponibles con la nueva experiencia de cliente de Skype empresarial. Para obtener más información sobre las nuevas características de Skype empresarial, consulte [descubrir Skype empresarial](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiencia de cliente Lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013 con la que los usuarios ya están familiarizados, pero presenta algunos cambios que los usuarios deben conocer. Para ver qué diferencias hay entre la experiencia del cliente de Lync y el cliente de Lync 2013, consulte [¿por qué veo Skype empresarial cuando estoy usando Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype Empresarial
<a name="usinglync"> </a>

Para que el entorno esté preparado para la actualización del cliente, debe realizar algunos cambios. Antes de empezar a realizar cambios para configurar la experiencia del cliente, primero debe asegurarse de que está usando una versión de Skype empresarial Server o Lync Server que admita la configuración de la Directiva de cliente.
  
Una vez que haya confirmado que está usando una versión de Skype empresarial Server o Lync Server que admita la configuración de la Directiva para controlar la experiencia del cliente, tendrá que establecer la configuración de la Directiva en su entorno. Los pasos específicos que necesita seguir dependen de la versión de Skype empresarial Server o de Lync Server que esté usando, y de si los usuarios son locales o conectados. 
  
Deseará realizar estos cambios antes de que la actualización de cliente se entregue a los usuarios para que pueda controlar la experiencia del cliente desde la primera vez que inicien el cliente de Skype empresarial. En las siguientes tablas se indican los pasos que debe seguir para configurar su entorno para la experiencia de cliente deseada para sus usuarios.
  
|**Deployment**|**Experiencia de cliente de Skype Empresarial**|**Experiencia de cliente Lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype Empresarial en línea](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype Empresarial Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Usar la experiencia del cliente de Skype con Lync Server 2013 o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar la experiencia del cliente de Lync con Lync Server 2013 o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia del cliente de Skype con Lync Server 2013 o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que admita la configuración de la Directiva de cliente.
  
- **Lync server 2013** : debe ejecutar la actualización acumulativa de diciembre 2014 (5.0.8308.857) para lync Server 2013 o una actualización posterior. Para obtener más información, consulte [actualizaciones para Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** : debe ejecutar la actualización acumulativa de febrero 2015 (4.0.7577.710) para lync Server 2010 o una actualización posterior. Para obtener más información, consulte [actualizaciones para Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Paso 2:** A continuación, use una directiva de cliente para configurar la experiencia del cliente de Skype con el cliente de Skype empresarial. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
  **Opción 1:** Establecer la experiencia de cliente Skype con una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de su implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia del cliente de Skype. Esto le permite asignar la experiencia del cliente Skype solo a aquellos usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opción 3:** Crear una nueva directiva para asignar a los usuarios que incluye la configuración de la experiencia de cliente Skype. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del parámetro  **Identity**:
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

A continuación, asigne la directiva a usuarios, usando el nombre de la directiva (el valor que ha usado para el parámetro **Identity**) como valor del parámetro **PolicyName**:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Paso 3:** Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia del cliente de Lync con Lync Server 2013 o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Esta es la experiencia predeterminada cuando el cliente de Skype empresarial se implementa en una implementación local de Lync Server. No es necesario configurar directivas de cliente para usarla experiencia de cliente Lync, pero puede controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la primera vez que los usuarios inician el cliente de Skype empresarial, se usa la experiencia del cliente de Skype y se muestra una notificación a los usuarios que le solicita que reinicien el cliente para obtener la experiencia del cliente de Lync. Puede configurar el entorno de modo que se muestre la experiencia de cliente Lync la primera vez que los usuarios inician el cliente y desactivar el tutorial de cliente modificando el registro del sistema en equipos cliente. Para conocer los pasos que debe realizar antes de implementar el cliente de Skype empresarial, consulte uno de los siguientes temas:
  
- **Lync server 2013**, consulte [configurar la experiencia de cliente con Skype empresarial en Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** consulte [configurar la experiencia de cliente con Skype empresarial en Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente Lync con Skype Empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente de Lync en una implementación local de Skype empresarial Server.
  
Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, implemente Skype empresarial Server.
  
 **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia del cliente de Lync con el cliente de Skype empresarial. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
 **Opción 1:** Establecer la experiencia de cliente Lync mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opción 3:** Crear una nueva directiva para asignar a los usuarios que incluye la configuración de la experiencia de cliente Lync. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor de parámetro **Identity**:
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

A continuación, asigne la directiva a usuarios, usando el nombre de la directiva (el valor que ha usado para el parámetro **Identity**) como valor del parámetro **PolicyName**:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Paso 3: opcional** : la primera vez que los usuarios inician el cliente de Skype empresarial, se usa la experiencia del cliente de Skype y se muestra una notificación a los usuarios pidiéndoles que reinicien el cliente para obtener la experiencia del cliente de Lync. Puede configurar su entorno para que se muestre la experiencia del cliente de Lync la primera vez que los usuarios inician el cliente, así como desactivar el tutorial del cliente, modificando el registro del sistema en los equipos cliente. Para conocer los pasos que debe realizar antes de implementar el cliente de Skype empresarial, consulte [configurar la experiencia de cliente con Skype empresarial](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Paso 4:** Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente Lync con Skype Empresarial en línea
<a name="LyncwithSfBO"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente de Lync y el uso de Skype empresarial online.
  
Si está usando Skype empresarial online, aún puede usar la experiencia del cliente de Lync con el cliente de Skype empresarial de su organización mediante PowerShell remoto para configurar directivas de cliente. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente. Tenga en cuenta que el nombre de la Directiva y del parámetro es diferente de la configuración que use para configurar la experiencia del cliente cuando use Skype empresarial o Lync Server local.
  
 **Opción 1:** Establezca la experiencia del cliente de Lync mediante una directiva global. Tenga en cuenta que las directivas de sitio y de cliente aplicadas a los usuarios tendrán prioridad sobre una directiva global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Use una instancia de directiva personalizada que incluya la configuración de la experiencia del cliente de Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
Para obtener información detallada sobre cómo configurar la experiencia de cliente con Skype empresarial online, incluidos los pasos sobre cómo controlar la primera experiencia de ejecución y los scripts de PowerShell que puede usar para configurar su entorno, consulte [cambiar entre las interfaces de usuario de Skype empresarial y del cliente de Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos que le ayudarán a preparar a su equipos de asistencia y a los usuarios finales para la actualización
<a name="support"> </a>

Para que le resulte más fácil para usted y su organización prepararse para la transición, contamos con muchos recursos adicionales disponibles para ayudarle a planificar, educar e integrar usuarios finales.
  
- [Vídeo: presentación de Skype empresarial](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guías de inicio rápido de Skype empresarial (descargar)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ahora es Skype empresarial: vea las novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype empresarial: guía paso a paso para usuarios nuevos](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué veo Skype empresarial cuando estoy usando Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

