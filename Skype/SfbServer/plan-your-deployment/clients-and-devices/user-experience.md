---
title: Planear la experiencia de cliente de Skype Empresarial 2015 para los usuarios
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre el nuevo Skype Empresarial y los pasos que puede seguir para preparar su entorno y sus usuarios para la actualización, independientemente de si usa Skype Empresarial Online, Skype Empresarial Server 2019, Skype Empresarial Server 2015, Lync Server 2013 o Lync Server 2010.'
ms.openlocfilehash: 1136bcf95a0c9ee045d9947bd7a2f7771dae16fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813930"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planear la experiencia de cliente de Skype Empresarial 2015 para los usuarios
 
**Resumen:** Obtenga información sobre el nuevo Skype Empresarial y los pasos que puede seguir para preparar su entorno y sus usuarios para la actualización, independientemente de si usa Skype Empresarial Online, Skype Empresarial Server 2019, Skype Empresarial Server 2015, Lync Server 2013 o Lync Server 2010.
  
La actualización de Office del 14 de abril de 2015 para Lync 2013 incluye la nueva interfaz de usuario de Skype Empresarial. Esta actualización permite a los administradores controlar la apariencia del cliente y elegir si conservar la experiencia de cliente de Lync 2013 o usar la experiencia de cliente de Skype Empresarial mejorada. El cliente de Skype Empresarial reemplazó efectivamente al cliente de Lync 2013 y agregó la capacidad de que los administradores elijan entre la experiencia de cliente de Lync existente y la nueva experiencia de cliente de Skype Empresarial. Para obtener información sobre esta actualización, vea la actualización del 14 de abril de [2015 para Lync 2013 (Skype Empresarial) (KB2889923).](https://support.microsoft.com/kb/2889923/)
  
El 12 de mayo de 2015 habrá otra actualización mensual de Office que incluye el cliente de Skype Empresarial actualizado. Muchos clientes que no aplicaron la actualización de abril recibirán la actualización del 12 de mayo para Office 2013. La información de este tema le ayudará a preparar la organización, el entorno y los usuarios para la actualización del cliente. Para facilitar la transición a los usuarios y equipos de soporte técnico, use la información de este tema para ayudarle a decidir qué experiencia de cliente desea para sus usuarios y, a continuación, realice los cambios en su entorno antes de implementar la actualización de cliente en su organización.
  
- [¿Qué experiencia de cliente desea para los usuarios?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el cliente de Skype Empresarial](user-experience.md#usinglync)
    
- [Recursos para ayudarle a preparar los equipos de soporte técnico y los usuarios finales para la actualización](user-experience.md#support)
    
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype Empresarial 2016. Antes de intentar configurar el entorno de cliente para usar el cliente de Lync 2013, compruebe la versión del cliente para asegurarse de que no comienza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para los usuarios?
<a name="clientexperience"> </a>

Con el nuevo cliente de Skype Empresarial, puede controlar qué experiencia de cliente obtienen sus usuarios, ya sea Lync o Skype Empresarial. La experiencia de cliente predeterminada depende de si usa Lync o Skype Empresarial local o en línea. Si usa Skype Empresarial Online (Lync Online) actualmente con Aplicaciones de Microsoft 365 para empresas, Microsoft 365 Empresa Standard u Office 2013, la experiencia de cliente de Skype Empresarial actualizada (que se inspira en la apariencia de Skype) será la experiencia de usuario predeterminada. Si usa Lync Server local actualmente, la experiencia de cliente de Lync será la predeterminada.
  
Puede configurar la experiencia de cliente que obtienen los usuarios mediante directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando inician sesión en Lync o Skype Empresarial.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype Empresarial

Además de todas las características de Lync, Skype Empresarial proporciona nuevas características con controles simplificados e iconos conocidos de Skype. Algunas características nuevas de Skype Empresarial solo están disponibles con la nueva experiencia de cliente de Skype Empresarial. Para obtener más información sobre las nuevas características de Skype Empresarial, consulte [Descubrir Skype Empresarial.](https://go.microsoft.com/fwlink/p/?LinkId=528686)
  
### <a name="lync-client-experience"></a>Experiencia de cliente lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013 con la que los usuarios ya están familiarizados, pero hay algunos cambios que querrá que los usuarios conozcan. Para ver las diferencias entre la experiencia del cliente lync y el cliente de Lync 2013, consulte ¿Por qué veo Skype Empresarial cuando uso [Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales que se incluyen más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype Empresarial
<a name="usinglync"> </a>

Hay algunas cosas que debe hacer para preparar el entorno para la actualización del cliente. Antes de empezar a realizar cambios para configurar la experiencia del cliente, primero debe asegurarse de que está usando una versión de Skype Empresarial Server o Lync Server que admita la configuración de directiva de cliente.
  
Una vez que haya confirmado que está usando una versión de Skype Empresarial Server o Lync Server que admita la configuración de directiva para controlar la experiencia del cliente, deberá configurar las opciones de directiva en su entorno. Los pasos específicos que debe seguir dependen de la versión de Skype Empresarial Server o Lync Server que use y de si los usuarios son locales o en línea. 
  
You'll want to make these changes before the client update is delivered to your users so that you can control the client experience from the first time they start the Skype for Business client. En las tablas siguientes se indican los pasos que debe seguir para configurar el entorno para la experiencia de cliente deseada para los usuarios.
  
|**Implementación**|**Experiencia de cliente de Skype Empresarial**|**Experiencia de cliente lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay pasos adicionales que no sean implementar la compilación 4711.1002 del cliente (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente de Lync con Skype Empresarial Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay pasos adicionales que no sean implementar la compilación 4711.1002 del cliente (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente lync con Skype Empresarial Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar la experiencia de cliente lync con Lync Server 2013 o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente de Skype en una implementación local. La experiencia predeterminada para local
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que admita la configuración de directiva de cliente.
  
- **Lync Server 2013:** debe ejecutar la actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013 o una actualización posterior. Para obtener información, [consulte Actualizaciones de Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
- **Lync Server 2010:** debe ejecutar la actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010 o una actualización posterior. Para obtener información, [consulte Actualizaciones de Lync Server 2010.](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
  **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente de Skype con el cliente de Skype Empresarial. Hay **3 opciones para usar** una directiva de cliente para establecer la experiencia del cliente.
  
  **Opción 1:** Establecer la experiencia de cliente de Skype mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opción 2:** Modifique una directiva de cliente existente que use en su entorno para incluir la configuración para habilitar la experiencia de cliente de Skype. Esto le permite asignar la experiencia de cliente de Skype solo a aquellos usuarios que tengan asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opción 3:** Cree una nueva directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente de Skype. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del **parámetro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

A continuación, asigne la directiva a los usuarios con el nombre de la directiva (el valor que usó para el parámetro **Identity)** como valor del **parámetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Paso 3:** Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente lync con Lync Server 2013 o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Esta es la experiencia predeterminada cuando el cliente de Skype Empresarial se implementa en una implementación local de Lync Server. No es necesario configurar ninguna directiva de cliente para usar la experiencia de cliente lync, pero es posible que desee controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la primera vez que los usuarios inician el cliente de Skype Empresarial, se usa la experiencia de cliente de Skype y se muestra una notificación a los usuarios que solicitan que reinicien el cliente para obtener la experiencia del cliente lync. Puede configurar su entorno para que la experiencia del cliente Lync se muestre la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial del cliente modificando el registro del sistema en los equipos cliente. Para ver los pasos que debe realizar antes de implementar el cliente de Skype Empresarial, consulte uno de los siguientes temas:
  
- **Lync Server 2013**, vea Configurar la experiencia de cliente con Skype Empresarial [en Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** vea Configurar la experiencia de cliente [con Skype Empresarial en Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente lync con Skype Empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente Lync en una implementación local de Skype Empresarial Server.
  
Siga los pasos de esta sección si desea configurar la experiencia de cliente de Skype en una implementación local. La experiencia predeterminada para local
  
 **Paso 1:** En primer lugar, implemente Skype Empresarial Server.
  
 **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente lync con el cliente de Skype Empresarial. Hay **3 opciones para usar** una directiva de cliente para establecer la experiencia del cliente.
  
 **Opción 1:** Establezca la experiencia de cliente lync mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente lync. Esto le permite asignar la experiencia de cliente lync solo a aquellos usuarios que tengan asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opción 3:** Cree una nueva directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente lync. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del **parámetro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

A continuación, asigne la directiva a los usuarios con el nombre de la directiva (el valor que usó para el parámetro **Identity)** como valor del **parámetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Paso 3: opcional:** de forma predeterminada, la primera vez que los usuarios inician el cliente de Skype Empresarial, se usa la experiencia de cliente de Skype y se muestra una notificación a los usuarios que les piden que reinicien el cliente para obtener la experiencia de cliente lync. Puede configurar el entorno para que la experiencia del cliente Lync se muestre la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial de cliente, modificando el registro del sistema en los equipos cliente. For the steps you need to perform before you deploy the Skype for Business client see [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Paso 4:** Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente de Lync con Skype Empresarial Online
<a name="LyncwithSfBO"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente lync y usa Skype Empresarial Online.
  
Si usa Skype Empresarial Online, puede seguir usando la experiencia de cliente de Lync con el cliente de Skype Empresarial de su organización con PowerShell remoto para configurar directivas de cliente. Hay **3 opciones para usar** una directiva de cliente para establecer la experiencia del cliente. Tenga en cuenta que los nombres de directiva y parámetro son diferentes de la configuración que se usa para configurar la experiencia de cliente cuando se usa Skype Empresarial o Lync Server local.
  
 **Opción 1:** Establezca la experiencia de cliente lync mediante una directiva global. Tenga en cuenta que las directivas de cliente y sitio aplicadas a los usuarios tendrán prioridad sobre una directiva global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente lync. Esto le permite asignar la experiencia de cliente lync solo a aquellos usuarios que tengan asignada la directiva existente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Use una instancia de directiva personalizada que incluya la configuración de la experiencia de cliente lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
Para obtener información detallada acerca de cómo configurar la experiencia de cliente con Skype Empresarial Online, incluidos los pasos para controlar la primera experiencia de ejecución y los scripts de PowerShell que puede usar para configurar su entorno, consulte Cambiar entre las [interfaces](https://aka.ms/SfBOUI)de usuario de cliente de Lync y Skype Empresarial.
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos para ayudarle a preparar los equipos de soporte técnico y los usuarios finales para la actualización
<a name="support"> </a>

Para facilitarle a usted y a su organización que se preparen para la transición, disponemos de muchos recursos adicionales que le ayudarán a planear, instruir e interactuar con los usuarios finales.
  
- [Video: presentación de Skype Empresarial](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guías de inicio rápido de Skype Empresarial (descarga)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync es ahora Skype Empresarial: ver las novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype Empresarial: guía paso a paso para nuevos usuarios](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué veo Skype Empresarial cuando uso Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

