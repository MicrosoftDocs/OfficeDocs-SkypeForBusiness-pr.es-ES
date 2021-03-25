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
description: "Summary: Learn about the new Skype for Business and the steps you can take to prepare your environment and your users for the update, whether you're using Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013, or Lync Server 2010."
ms.openlocfilehash: 4f61876ab9826644fb7ef22db99d54adb2afe403
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112806"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planear la experiencia de cliente de Skype Empresarial 2015 para los usuarios
 
**Resumen:** Obtenga información sobre el nuevo Skype Empresarial y los pasos que puede seguir para preparar su entorno y los usuarios para la actualización, tanto si usa Skype Empresarial Online, Skype Empresarial Server 2019, Skype Empresarial Server 2015, Lync Server 2013 o Lync Server 2010.
  
La actualización de Office para Lync 2013 del 14 de abril de 2015 incluye la nueva interfaz de usuario de Skype Empresarial. Esta actualización permite a los administradores controlar la apariencia del cliente y elegir si conservar la experiencia de cliente de Lync 2013 o usar la experiencia de cliente de Skype Empresarial mejorada. El cliente de Skype Empresarial reemplazó eficazmente al cliente de Lync 2013 y agregó la capacidad para que los administradores elijan entre la experiencia de cliente de Lync existente y la nueva experiencia del cliente de Skype Empresarial. Para obtener información sobre esta actualización, vea actualización del 14 de abril de [2015 para Lync 2013 (Skype Empresarial) (KB2889923).](https://support.microsoft.com/kb/2889923/)
  
El 12 de mayo de 2015 habrá otra actualización mensual de Office que incluya el cliente de Skype Empresarial actualizado. Muchos clientes que no aplicaron la actualización de abril recogerán la actualización del 12 de mayo para Office 2013. La información de este tema le ayudará a preparar su organización, su entorno y los usuarios para la actualización del cliente. Para facilitar la transición a los usuarios y los equipos de soporte técnico, use la información de este tema para ayudarle a decidir qué experiencia de cliente desea para los usuarios y, a continuación, realizar los cambios en el entorno antes de implementar la actualización de cliente en su organización.
  
- [¿Qué experiencia de cliente desea para los usuarios?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el cliente de Skype Empresarial](user-experience.md#usinglync)
    
- [Recursos que le ayudarán a preparar los equipos de soporte técnico y los usuarios finales para la actualización](user-experience.md#support)
    
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype Empresarial 2016. Antes de intentar configurar el entorno de cliente para que use el cliente de Lync 2013, compruebe la versión del cliente para asegurarse de que no comienza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para los usuarios?
<a name="clientexperience"> </a>

Con el nuevo cliente de Skype Empresarial, puede controlar qué experiencia de cliente obtienen los usuarios, ya sea Lync o Skype Empresarial. La experiencia de cliente predeterminada depende de si usa Lync o Skype Empresarial local o en línea. Si está usando Skype Empresarial Online (Lync Online) hoy con Aplicaciones de Microsoft 365 para empresas, Microsoft 365 Empresa Standard u Office 2013, la experiencia actualizada de cliente de Skype Empresarial, inspirada en la apariencia de Skype, será la experiencia de usuario predeterminada. Si usa Lync Server local hoy, la experiencia del cliente de Lync será la predeterminada.
  
Puede configurar la experiencia del cliente que obtienen los usuarios mediante directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando inician sesión en Lync o Skype Empresarial.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype Empresarial

Además de todas las características de Lync, Skype Empresarial proporciona nuevas características con controles simplificados e iconos conocidos de Skype. Algunas características nuevas de Skype Empresarial solo están disponibles con la nueva experiencia de cliente de Skype Empresarial. Para obtener más información sobre las nuevas características de Skype Empresarial, vea [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiencia de cliente de Lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013 con la que los usuarios ya están familiarizados, pero hay algunos cambios que querrá que los usuarios conozcan. Para ver las diferencias entre la experiencia de cliente de Lync y el cliente de Lync 2013, vea ¿Por qué veo Skype Empresarial cuando estoy usando [Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype Empresarial
<a name="usinglync"> </a>

Hay algunas cosas que tendrá que hacer para preparar el entorno para la actualización del cliente. Antes de empezar a realizar cambios para configurar la experiencia del cliente, primero debe asegurarse de que está usando una versión de Skype Empresarial Server o Lync Server que admita la configuración de directiva de cliente.
  
Una vez que haya confirmado que está usando una versión de Skype Empresarial Server o Lync Server que admita la configuración de directiva para controlar la experiencia del cliente, deberá configurar la configuración de directiva en su entorno. Los pasos específicos que debe seguir dependen de la versión de Skype Empresarial Server o Lync Server que está usando y de si los usuarios son locales o en línea. 
  
Querrá realizar estos cambios antes de que la actualización del cliente se entregue a los usuarios para que pueda controlar la experiencia del cliente desde la primera vez que inicien el cliente de Skype Empresarial. En las tablas siguientes se indican los pasos que debe seguir para configurar el entorno para la experiencia de cliente deseada para los usuarios.
  
|**Implementación**|**Experiencia de cliente de Skype Empresarial**|**Experiencia de cliente de Lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay otros pasos que no sean implementar la compilación de cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente de Lync con Skype Empresarial Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay otros pasos que no sean implementar la compilación de cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente de Lync con Skype Empresarial Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar la experiencia de cliente de Lync con Lync Server 2013 o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente de Skype con Lync Server 2013 o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente de Skype en una implementación local. La experiencia predeterminada para locales
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que admita la configuración de directiva de cliente.
  
- **Lync Server 2013:** debe ejecutar la actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013 o una actualización posterior. Para obtener información, vea [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010:** debe ejecutar la actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010 o una actualización posterior. Para obtener información, vea [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente de Skype con el cliente de Skype Empresarial. Hay **3 opciones para** usar una directiva de cliente para establecer la experiencia del cliente.
  
  **Opción 1:** Establezca la experiencia de cliente de Skype mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de usuario y de nivel de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente de Skype. Esto le permite asignar la experiencia de cliente de Skype solo a los usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opción 3:** Cree una nueva directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente de Skype. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del **parámetro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

A continuación, asigne la directiva a los usuarios, usando el nombre de la directiva (el valor que usó para el parámetro **Identity)** como el valor del **parámetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Paso 3:** Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, cree 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia de cliente de Lync con Lync Server 2013 o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Esta es la experiencia predeterminada cuando el cliente de Skype Empresarial se implementa en una implementación local de Lync Server. No es necesario configurar ninguna directiva de cliente para usar la experiencia de cliente de Lync, pero es posible que desee controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la primera vez que los usuarios inician el cliente de Skype Empresarial, se usa la experiencia del cliente de Skype y se muestra una notificación a los usuarios que solicitan que reinicien el cliente para obtener la experiencia del cliente de Lync. Puede configurar el entorno para que se muestre la experiencia del cliente de Lync la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial del cliente modificando el Registro del sistema en los equipos cliente. Para ver los pasos que debe realizar antes de implementar el cliente de Skype Empresarial, consulte uno de los siguientes temas:
  
- **Lync Server 2013**, vea [Configure the client experience with Skype for Business in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010** vea [Configure the client experience with Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente de Lync con Skype Empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente de Lync en una implementación local de Skype Empresarial Server.
  
Siga los pasos de esta sección si desea configurar la experiencia de cliente de Skype en una implementación local. La experiencia predeterminada para locales
  
 **Paso 1:** En primer lugar, implemente Skype Empresarial Server.
  
 **Paso 2:** A continuación, use una directiva de cliente para establecer la experiencia de cliente de Lync con el cliente de Skype Empresarial. Hay **3 opciones para** usar una directiva de cliente para establecer la experiencia del cliente.
  
 **Opción 1:** Establezca la experiencia de cliente de Lync mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de usuario y de nivel de sitio tienen prioridad sobre la directiva global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente de Lync. Esto le permite asignar la experiencia de cliente de Lync solo a los usuarios que tienen asignada la directiva existente:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opción 3:** Cree una nueva directiva para asignar a los usuarios que incluya la configuración de la experiencia de cliente de Lync. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del **parámetro Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

A continuación, asigne la directiva a los usuarios, usando el nombre de la directiva (el valor que usó para el parámetro **Identity)** como el valor del **parámetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Paso 3: opcional:** de forma predeterminada, la primera vez que los usuarios inician el cliente de Skype Empresarial, se usa la experiencia del cliente de Skype y se muestra una notificación a los usuarios pidiéndoles que reinicien el cliente para obtener la experiencia del cliente de Lync. Puede configurar el entorno para que la experiencia del cliente de Lync se muestre la primera vez que los usuarios inicien el cliente, así como desactivar el tutorial del cliente, modificando el Registro del sistema en los equipos cliente. Para ver los pasos que debe realizar antes de implementar el cliente de Skype Empresarial, vea [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Paso 4:** Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, cree 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente de Lync con Skype Empresarial Online
<a name="LyncwithSfBO"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente de Lync y usar Skype Empresarial Online.
  
Si usa Skype Empresarial Online, puede seguir usando la experiencia de cliente de Lync con el cliente de Skype Empresarial en su organización mediante PowerShell remoto para configurar directivas de cliente. Hay **3 opciones para** usar una directiva de cliente para establecer la experiencia del cliente. Tenga en cuenta que los nombres de directiva y parámetro son diferentes de la configuración que se usa para configurar la experiencia del cliente cuando se usa Skype Empresarial o Lync Server local.
  
 **Opción 1:** Establezca la experiencia de cliente de Lync mediante una directiva global. Tenga en cuenta que las directivas de cliente y sitio aplicadas a los usuarios tendrán prioridad sobre una directiva global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modifique una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente de Lync. Esto le permite asignar la experiencia de cliente de Lync solo a los usuarios que tienen asignada la directiva existente:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Use una instancia de directiva personalizada que incluya la configuración de la experiencia de cliente de Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Después de configurar las directivas de cliente, implemente el cliente de Skype Empresarial, cree 4711.1002 (abril de 2015) o posterior.
  
Para obtener información detallada sobre cómo configurar la experiencia del cliente con Skype Empresarial Online, incluidos los pasos sobre cómo controlar la primera experiencia de ejecución y los scripts de PowerShell que puede usar para configurar el entorno, vea [Switching between the Skype for Business](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)and the Lync client user interfaces .
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos que le ayudarán a preparar los equipos de soporte técnico y los usuarios finales para la actualización
<a name="support"> </a>

Para que sea más fácil para usted y su organización prepararse para la transición, tenemos muchos recursos adicionales disponibles para ayudarle a planear, educar e interactuar con los usuarios finales.
  
- [Video: presentación de Skype Empresarial](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guías de inicio rápido de Skype Empresarial (descarga)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync es ahora Skype Empresarial: vea las novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype Empresarial: guía paso a paso para nuevos usuarios](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué veo Skype Empresarial cuando uso Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
