---
title: Planear la experiencia de cliente de Skype empresarial 2015 para los usuarios
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
description: 'Resumen: Obtenga información sobre el nuevo Skype empresarial y los pasos que puede realizar para preparar el entorno y los usuarios para la actualización, si está usando Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015, Lync Server 2013 o Lync Server 2010.'
ms.openlocfilehash: c54465b2f2c6cb7fb8d131b52de27c3f64d0bcc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028011"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planear la experiencia de cliente de Skype empresarial 2015 para los usuarios
 
**Resumen:** Obtenga información sobre el nuevo Skype empresarial y los pasos que puede realizar para preparar el entorno y los usuarios para la actualización, si está usando Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015, Lync Server 2013 o Lync Server 2010.
  
La actualización del 14 de abril de 2015 Office para Lync 2013 incluye la nueva interfaz de usuario de Skype empresarial. Esta actualización permite a los administradores controlar la apariencia del cliente y elegir si desea conservar la experiencia del cliente de Lync 2013 o usar la experiencia de cliente de Skype empresarial mejorada. El cliente de Skype empresarial ha reemplazado de manera efectiva el cliente de Lync 2013 y ha agregado la capacidad de que los administradores elijan entre la experiencia del cliente de Lync existente y la nueva experiencia de cliente de Skype empresarial. Para obtener información sobre esta actualización, consulte [actualización del 14 de abril de 2015 para Lync 2013 (Skype empresarial) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
El 12 de mayo de 2015 habrá otra actualización mensual de Office que incluya el cliente de Skype empresarial actualizado. Muchos clientes que no aplicaron la actualización de abril recibirán la actualización de mayo 12 para Office 2013. La información de este tema le ayudará a preparar la organización, el entorno y los usuarios para la actualización del cliente. Para facilitar la transición a los usuarios y a los equipos de soporte técnico, use la información de este tema para ayudarle a decidir qué experiencia de cliente desea para los usuarios y, a continuación, realizar los cambios en el entorno antes de implementar la actualización de cliente en la organización.
  
- [¿Qué experiencia de cliente desea para los usuarios?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el cliente de Skype empresarial](user-experience.md#usinglync)
    
- [Recursos que le ayudarán a preparar a sus equipos de soporte técnico y a los usuarios finales para la actualización](user-experience.md#support)
    
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de intentar configurar el entorno del cliente para usar el cliente Lync 2013, Compruebe la versión del cliente para asegurarse de que no empieza con el número 16; por ejemplo: 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para los usuarios?
<a name="clientexperience"> </a>

Con el nuevo cliente de Skype empresarial, puede controlar la experiencia de cliente que los usuarios obtienen, ya sea Lync o Skype empresarial. La experiencia de cliente predeterminada depende de si usa Lync o Skype empresarial local o en línea. Si usa Skype empresarial online (Lync Online) en la actualidad con Office 365 ProPlus, Office 365 empresa Premium u Office 2013, la experiencia de usuario de Skype empresarial actualizada (inspirado en la apariencia de Skype) será la experiencia de usuario predeterminada. Si usa actualmente Lync Server local, la experiencia de cliente de Lync será el valor predeterminado.
  
Puede configurar la experiencia del cliente que obtienen los usuarios mediante directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando inician sesión en Lync o Skype empresarial.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype empresarial

Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados e iconos conocidos de Skype. Algunas características nuevas de Skype empresarial solo están disponibles con la nueva experiencia de cliente de Skype empresarial. Para obtener más información sobre las nuevas características de Skype empresarial, consulte [Descubra Skype empresarial](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiencia de cliente Lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013, con la que los usuarios ya están familiarizados, pero hay algunos cambios que querrá informar a los usuarios sobre. Para ver las diferencias entre la experiencia del cliente de Lync y el cliente de Lync 2013, consulte [¿por qué veo Skype empresarial cuando uso Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype empresarial
<a name="usinglync"> </a>

Hay algunas cosas que debe hacer para preparar su entorno para la actualización de cliente. Antes de comenzar a realizar cambios para configurar la experiencia del cliente, primero debe asegurarse de que está usando una versión de Skype empresarial Server o Lync Server que admita la configuración de la Directiva de cliente.
  
Una vez que haya confirmado que está usando una versión de Skype empresarial Server o Lync Server que admita la configuración de la Directiva para controlar la experiencia del cliente, deberá configurar las opciones de la Directiva en su entorno. Los pasos específicos que debe seguir dependen de la versión de Skype empresarial Server o Lync Server que esté usando, y de si los usuarios están en línea o en una ubicación local. 
  
Querrá realizar estos cambios antes de que la actualización de cliente se entregue a los usuarios para que pueda controlar la experiencia de cliente desde la primera vez que inicien el cliente de Skype empresarial. En las siguientes tablas se indican los pasos que debe seguir para configurar el entorno para la experiencia de cliente deseada para los usuarios.
  
|**Implementación**|**Experiencia de cliente de Skype empresarial**|**Experiencia de cliente Lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay otros pasos adicionales que implementar la compilación de cliente 4711,1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype empresarial online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay otros pasos adicionales que implementar la compilación de cliente 4711,1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype empresarial Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar la experiencia de cliente Lync con Lync Server 2013 o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente de Skype en una implementación local. La experiencia predeterminada para local
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que admita la configuración de la Directiva de cliente.
  
- **Lync server 2013** : debe ejecutar la actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013 o una actualización posterior. Para obtener más información, consulte [actualizaciones para Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** : debe ejecutar la actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010 o una actualización posterior. Para obtener más información, consulte [actualizaciones para Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente de Skype con el cliente de Skype empresarial. Hay **tres opciones** para usar una directiva de cliente para establecer la experiencia del cliente.
  
  **Opción 1:** Establecer la experiencia de cliente de Skype con una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente de Skype. Esto le permite asignar la experiencia de cliente de Skype solo a los usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opción 3:** Cree una nueva Directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente de Skype. En primer lugar, cree la nueva Directiva de cliente y proporcione el nombre de la Directiva como valor del parámetro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

A continuación, asigne la Directiva a los usuarios, usando el nombre de la Directiva (el valor que usó para el parámetro **Identity** ) como valor del parámetro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Paso 3:** Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente Lync con Lync Server 2013 o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Esta es la experiencia predeterminada cuando el cliente de Skype empresarial se implementa en una implementación local de Lync Server. No es necesario configurar ninguna directiva de cliente para usar la experiencia de cliente Lync, pero es posible que desee controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la experiencia de cliente de Skype se usa la primera vez que los usuarios inician el cliente de Skype empresarial y se muestra una notificación a los usuarios que solicita que reinicien el cliente para obtener la experiencia de cliente Lync. Puede configurar el entorno para que la experiencia de cliente de Lync se muestre la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial del cliente modificando el registro del sistema en los equipos cliente. Para conocer los pasos que debe realizar antes de implementar el cliente de Skype empresarial, consulte uno de los siguientes temas:
  
- **Lync server 2013**, consulte [configurar la experiencia de cliente con Skype empresarial en Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** consulte [configurar la experiencia de cliente con Skype empresarial en Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente Lync con Skype empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente Lync en una implementación local de Skype empresarial Server.
  
Siga los pasos de esta sección si desea configurar la experiencia del cliente de Skype en una implementación local. La experiencia predeterminada para local
  
 **Paso 1:** En primer lugar, implemente Skype empresarial Server.
  
 **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente Lync con el cliente de Skype empresarial. Hay **tres opciones** para usar una directiva de cliente para establecer la experiencia del cliente.
  
 **Opción 1:** Establezca la experiencia de cliente Lync mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opción 3:** Cree una nueva Directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente de Lync. En primer lugar, cree la nueva Directiva de cliente y proporcione el nombre de la Directiva como valor del parámetro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

A continuación, asigne la Directiva a los usuarios, usando el nombre de la Directiva (el valor que usó para el parámetro **Identity** ) como valor del parámetro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Paso 3: opcional** -de manera predeterminada, la primera vez que los usuarios inician el cliente de Skype empresarial, se usa la experiencia de cliente de Skype y se muestra una notificación a los usuarios pidiéndoles que reinicien el cliente para obtener la experiencia del cliente de Lync. Puede configurar el entorno para que la experiencia de cliente de Lync se muestre la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial del cliente, modificando el registro del sistema en los equipos cliente. Para conocer los pasos que debe realizar antes de implementar el cliente de Skype empresarial, consulte [configurar la experiencia de cliente con Skype empresarial](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Paso 4:** Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente Lync con Skype empresarial online
<a name="LyncwithSfBO"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente Lync y el uso de Skype empresarial online.
  
Si usa Skype empresarial online, puede seguir usando la experiencia de cliente Lync con el cliente de Skype empresarial en su organización mediante PowerShell remoto para configurar directivas de cliente. Hay **tres opciones** para usar una directiva de cliente para establecer la experiencia del cliente. Tenga en cuenta que los nombres de directiva y parámetro son distintos de los valores que usa para configurar la experiencia del cliente cuando usa Skype empresarial o Lync Server local.
  
 **Opción 1:** Establezca la experiencia de cliente Lync mediante una directiva global. Tenga en cuenta que las directivas de cliente y sitio que se aplican a los usuarios tendrán prioridad sobre una directiva global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Usar una instancia de directiva personalizada que incluye la configuración de la experiencia de cliente de Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Una vez que haya configurado las directivas de cliente, implemente el cliente de Skype empresarial, compilación 4711,1002 (abril de 2015) o posterior.
  
Para obtener información detallada sobre cómo configurar la experiencia de cliente con Skype empresarial online, incluidos los pasos para controlar la primera experiencia de ejecución y los scripts de PowerShell que puede usar para configurar su entorno, consulte [alternar entre las interfaces de usuario del cliente de Skype empresarial y Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos que le ayudarán a preparar a sus equipos de soporte técnico y a los usuarios finales para la actualización
<a name="support"> </a>

Para que sea más fácil para usted y para su organización prepararse para la transición, tenemos muchos recursos adicionales disponibles para ayudarle a planificar, educar y atraer a los usuarios finales.
  
- [Video: presentación de Skype Empresarial](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guías de inicio rápido de Skype empresarial (descargar)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ahora es Skype empresarial: vea las novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype empresarial: guía paso a paso para nuevos usuarios](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué veo Skype empresarial cuando uso Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

