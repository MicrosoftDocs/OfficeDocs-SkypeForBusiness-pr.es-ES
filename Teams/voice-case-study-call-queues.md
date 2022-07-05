---
title: 'Caso práctico de Voz de Contoso de Teams: Operadores automáticos y colas de llamadas'
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
description: 'Caso práctico de voz de Teams para empresas multinacionales: operadores automáticos y colas de llamadas'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615846"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Caso práctico de Contoso: Operadores automáticos y colas de llamadas

Contoso estaba familiarizado con los operadores automáticos y las colas de llamadas desde su implementación local Skype Empresarial. Para comprender cómo configurar las colas de llamadas y los operadores automáticos en la nube, revisaron [Planear los operadores automáticos y las colas de llamadas de Teams](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Requisitos según el tipo de sitio

Según el tipo de sitio, Contoso tenía las siguientes necesidades:

- Tipo de sitio A: Sistemas de telefonía heredados tradicionales 

  Tipo de sitio A necesario para mantener el mismo número de teléfono asociado al recepcionista que el número de sus operadores automáticos. Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se enrutarían a los miembros del equipo. Había una mezcla de sitios que utilizaban sistema telefónico con enrutamiento directo y sistema telefónico con planes de llamadas.  

- Tipo de sitio B: Skype Empresarial Telefonía IP empresarial 

  El tipo de sitio B tenía operadores automáticos y colas de llamadas existentes que era necesario migrar a Teams. Contoso necesita mantener los números de teléfono asociados a los operadores automáticos. Contoso movió la mayoría de estos sitios a Sistema telefónico con planes de llamada. Sin embargo, en las pocas ubicaciones donde planes de llamadas no estaba disponible, Contoso movió estos sitios a una configuración de enrutamiento directo.  

- Tipo de sitio C: Skype Empresarial Telefonía IP empresarial & sistema de telefonía heredado tradicional 

  El tipo de sitio C tenía operadores automáticos existentes que residían en el sistema de telefonía heredado tradicional. Las decisiones y configuraciones para este sitio eran las mismas que las del tipo de sitio A.   

- Para todos los tipos de sitio, Contoso hizo las siguientes preguntas:

  - P: ¿Usaremos números nuevos o existentes? 
    R: Contoso decidió usar los números de teléfono existentes para asignarse a la cuenta de servicio del operador automático. 

  - P: ¿Cuándo estará disponible el operador automático para aceptar llamadas entrantes? 
    R: Contoso decidió establecer el horario laboral y que las llamadas recibidas fuera del horario laboral se redirijan a un operador automático "fuera del horario laboral".  

  - P: ¿Cómo se enrutarán las llamadas a los miembros de una cola de llamadas: operador, enrutamiento serial o round robin? 
    R: Contoso decidió usar el enrutamiento de Attendant, 

  - P: ¿Cómo determinaremos cuándo debe o no recibirse una llamada un usuario? 
    R: Contoso decidió usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia. 

## <a name="configuration"></a>Configuración

Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en [Administrar cuentas de recursos](manage-resource-accounts.md):

1. Obtenga un número de servicio.

2. Obtenga una licencia gratuita **Teléfono Microsoft Teams cuenta de recursos** o una licencia de sistema telefónico de pago para usarla con la cuenta de recursos o una licencia de Sistema telefónico.

3. Cree la cuenta de recursos. Se requiere un operador automático o una cola de llamadas para tener una cuenta de recursos asociada.

4. Asigne una licencia **de cuenta** de recursos **de Teléfono Teams Estándar o Teléfono Microsoft Teams** a la cuenta de recursos. Para obtener más información, vea [Teléfono Microsoft Teams licencia de cuenta de recursos](./teams-add-on-licensing/virtual-user.md).

5. Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias.

6. Cree una cola de llamadas o un operador automático del sistema telefónico.

7. Vincule la cuenta de recursos con una cola de llamadas o un operador automático.

### <a name="sites-with-phone-system-with-direct-routing"></a>Sitios con sistema telefónico con enrutamiento directo

Contoso tuvo que configurar el número de teléfono proporcionado por el operador local como el número de servicio en Office 365.

- Para configurar un número de teléfono disponible mediante enrutamiento directo, Contoso siguió las instrucciones que se encuentran en [Administrar cuentas de recursos](manage-resource-accounts.md). Como Office 365 no conoce los números de teléfono locales, Contoso usó PowerShell para completar la configuración.   

- Para configurar el operador automático de la nube, Contoso siguió los pasos descritos en [Configurar un operador automático](create-a-phone-system-auto-attendant.md) en la nube. 

- Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas](create-a-phone-system-call-queue.md) en la nube.  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sitios con sistema telefónico con plan de llamadas

Contoso tuvo que transferir el número de teléfono que se usó para Skype Empresarial Telefonía IP empresarial operadores automáticos a Sistema telefónico de Office 365. Esto permitió que se asignara el mismo número como número de servicio para usarlo como operador automático. 

- Para realizar la portabilidad del número de teléfono, Contoso siguió las instrucciones de [Transferir números de teléfono a Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) y obtuvo instrucciones adicionales en [Administrar números de teléfono para su organización](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para configurar un operador automático de la nube, Contoso siguió los pasos descritos en [Configurar un operador automático](create-a-phone-system-auto-attendant.md) en la nube.

-  Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas](create-a-phone-system-call-queue.md) en la nube.  

