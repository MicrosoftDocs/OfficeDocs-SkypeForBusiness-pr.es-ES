---
title: Caso práctico de voz de Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786096"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Caso práctico de Contoso: los operadores automáticos y las colas de llamadas

Contoso está familiarizado con los operadores automáticos y las colas de llamadas desde su implementación local de Skype empresarial. Para comprender cómo se configuran los operadores automáticos de la nube, revisan [Qué son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [ejemplo de Small Business-configurar tutorial de operador automático](tutorial-org-aa.yml). Para obtener más información sobre las opciones disponibles para configurar las colas de llamadas, contoso ha revisado [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).  

## <a name="requirements-depending-on-site-type"></a>Requisitos según el tipo de sitio

Según el tipo de sitio, contoso tuvo las siguientes necesidades:

- Tipo de sitio A: sistemas tradicionales de telefonía heredados 

  Tipo de sitio a necesario para mantener el mismo número de teléfono asociado a la recepcionista que el número de sus operadores automáticos. Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se dirigirían a los miembros del equipo. Había una combinación de sitios que usaban el sistema telefónico con enrutamiento directo y sistema telefónico con planes de llamadas.  

- Tipo de sitio B: voz de Skype empresarial Enterprise 

  El tipo de sitio B tenía operadores automáticos y colas de llamadas que necesitaban migrar a teams. Contoso necesitaba mantener los números de teléfono asociados con los operadores automáticos. Contoso movió la mayoría de estos sitios a un sistema telefónico con planes de llamadas. Sin embargo, en las pocas ubicaciones en las que los planes de llamadas no estaban disponibles, contoso movió estos sitios a una configuración de enrutamiento directo.  

- Tipo de sitio C: Skype empresarial Voice & sistema de telefonía tradicional tradicional 

  El tipo de sitio C tenía operadores automáticos existentes que residían en el sistema de telefonía tradicional heredado. Las decisiones y configuraciones de este sitio eran las mismas que las del tipo A.   

- Para todos los tipos de sitios, contoso preguntó las siguientes preguntas:

  - P: ¿usaremos números nuevos o existentes? 
    A: contoso decidió usar números de teléfono existentes para asignarlos a la cuenta de servicio del operador automático. 

  - P: ¿Cuándo estará disponible el operador automático para aceptar las llamadas entrantes? 
    A: contoso decidió establecer las horas laborales y recibir llamadas después de las horas de oficina redirigidas a un operador automático "fuera del horario".  

  - P: ¿cómo se enrutarán las llamadas a los miembros en una cola de llamadas: operador, serie o enrutamiento Round Robin? 
    A: contoso decidió usar el enrutamiento de operador, 

  - P: ¿cómo determinamos Cuándo un usuario debería o no recibir una llamada? 
    A: contoso decidió usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia. 


## <a name="configuration"></a>Configuración

Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en [administrar cuentas de recursos](manage-resource-accounts.md): 

1. Obtener un número de servicio. 

2. Obtener un sistema telefónico gratis: licencia de usuario virtual o una licencia de sistema telefónico de pagos para usar con la cuenta de recursos o una licencia de sistema telefónico.

3. Crear la cuenta de recursos. Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas. 

4. Asigne el sistema telefónico o un sistema telefónico (licencia de usuario virtual) a la cuenta de recursos. Para obtener más información, consulte [Microsoft 365 Phone System-virtual User License](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).

5. Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias. 

6. Crear una cola de llamadas de sistema telefónicas o un operador automático 

7. Vincular la cuenta de recursos con una cola de llamadas o un operador automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sitios con sistema telefónico con enrutamiento directo 

Contoso tenía que configurar el número de teléfono proporcionado por el operador local como número de servicio en Office 365. 

- Para configurar un número de teléfono disponible mediante enrutamiento directo, contoso siguió las instrucciones que se encuentran en [administrar cuentas de recursos](manage-resource-accounts.md). Puesto que Office 365 no reconoce los números de teléfono locales, contoso usó PowerShell para completar la configuración.   

- Para configurar el operador automático de la nube, contoso siguió los pasos indicados en [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md). 

- Para configurar una cola de llamadas en la nube, contoso siguió los pasos indicados en [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sitios con sistema telefónico con plan de llamadas

Contoso tenía que migrar el número de teléfono que se usó para los operadores automáticos de Skype empresarial Enterprise Voice al sistema telefónico de Office 365. Permite que el mismo número se asigne como un número de servicio para usarlo como un operador automático. 

- Para migrar el número de teléfono, contoso siguió las instrucciones de [transferir números de teléfono a teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) y obtener instrucciones adicionales [para administrar los números de teléfono de su organización](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

- Para configurar un operador automático de la nube, contoso siguió los pasos indicados en [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).

-  Para configurar una cola de llamadas en la nube, contoso siguió los pasos indicados en [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).  

 