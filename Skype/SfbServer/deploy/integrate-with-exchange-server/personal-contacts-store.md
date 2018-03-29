---
title: Configurar el almacén de contactos personales en equipos cliente para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal utilizado por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a>Configurar el almacén de contactos personales en equipos cliente para Skype Empresarial Server 2015
 
**Resumen:** Configurar el almacén de contactos personal utilizado por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.
  
Si está integrando Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, debe configurar el almacén de contactos personal en los equipos cliente ejecutan Skype para el negocio. En concreto, debe configurar Skype para negocio utiliza Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.
  
Tenga en cuenta que esto no es necesario en equipos con Skype para el negocio.
  
Para configurar este valor en un solo equipo, siga este procedimiento:
  
1. En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.
    
2. En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.
    
3. En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.
    
4. Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.
    
5. Después de crea el nuevo valor, escriba PersonalContactStoreOverride y, a continuación, presione ENTRAR para cambiar el nombre del valor.
    
6. Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.
    
Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener más información, consulte la documentación de directiva de grupo en [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

