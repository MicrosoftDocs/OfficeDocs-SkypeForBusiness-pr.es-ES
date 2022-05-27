---
title: Configurar Conexión con operador
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Más información sobre cómo configurar Conexión con operador.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d3b56a7935f31413829c89285fc81ee70023ab4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675772"
---
# <a name="configure-operator-connect"></a>Configurar Conexión con operador

En este artículo se describe cómo configurar Conexión con operador. Antes de configurar Conexión con operador, asegúrese de leer [Planear Conexión con operador](operator-connect-plan.md) para obtener información sobre los requisitos previos y las licencias.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el centro de administración de Teams. En el panel de navegación izquierdo, vaya a **Operadores de > de voz**.

Para habilitar un operador:

1. **Elige un operador.** En la pestaña **Todos los operadores** , filtre los operadores disponibles por región o servicio para encontrar el operador adecuado para sus necesidades de voz. A continuación, selecciona el operador que quieras habilitar.  

2. **Seleccione países.** En **Configuración del operador**, selecciona los países que quieras habilitar con el operador seleccionado.

3. **Proporcionar información de contacto** Tu información de contacto, incluyendo tu nombre completo y dirección de correo electrónico, se compartirá automáticamente con tu operador. Puede cambiar esta información más adelante. Además, tendrás que proporcionar el tamaño de la empresa y tendrás la opción de proporcionar tu número de teléfono. Los operadores utilizarán esta información para ponerse en contacto con usted con más detalles sobre Conexión con operador.

4. Acepta el aviso de transferencia de datos.

5. **Agrega tu operador.** Selecciona **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

La manera de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo los números existentes de los planes de llamadas de Microsoft o del enrutamiento directo.

- Si necesita adquirir números de teléfono para nuevos usuarios, consulte [Adquirir números para nuevos usuarios de Teams](#acquire-numbers-for-new-teams-users).

- Si desea mover números existentes de Planes de llamadas a Conexión con operador, vea [Mover números de planes de llamadas a Conexión con operador](#move-numbers-from-calling-plans-to-operator-connect).

- Si desea mover números existentes de Enrutamiento directo a Conexión con operador, vea [Mover números de Enrutamiento directo a Conexión con operador](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos usuarios de Teams

Para adquirir números para nuevos usuarios de Teams, siga estos pasos:

1. **Asignar una licencia de Sistema telefónico.** Puede asignar una licencia de Sistema telefónico a los usuarios desde la Centro de administración de Microsoft 365 o mediante PowerShell. Para obtener más información, vea [Asignar licencias de complementos de Teams a usuarios](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Los usuarios a los que se les asignarán números de teléfono adquiridos con Conexión con operador deben estar en el modo TeamsOnly. Si su organización está en modo TeamsOnly, todos los usuarios se encuentran en el modo TeamsOnly. Para comprobarlo, en el centro de administración de Teams, vaya a **Teams > Teams configuración de actualización**. Si su organización está en modo Islas, compruebe si determinados usuarios están en modo TeamsOnly. Vaya a **Usuarios** y seleccione una cuenta de usuario. En la pestaña **Cuenta**, en **Teams actualización,** el modo de coexistencia debe establecerse en "TeamsOnly".

3. **Adquirir números.** Ve al sitio web de tu operador para pedir y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, ve al [directorio de Microsoft 365 Conexión con operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

4. **Asignar números.** Una vez que el operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de > Teléfono de voz**. Asigne números a los usuarios desde el centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

> [!NOTE]
> Además de [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md), puede obtener números de teléfono gratuitos o de pago para servicios como Audioconferencia (para puentes de conferencia), operadores automáticos y colas de llamadas (también denominados números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede administrar cientos de llamadas simultáneamente, mientras que el número de teléfono de un usuario solo puede atender algunas llamadas simultáneamente. Para obtener números de servicio, ponte en contacto con tu operador.

### <a name="emergency-addresses"></a>Direcciones de emergencia

La dirección de emergencia es una ubicación estática asociada a un número. Una vez creadas las direcciones de emergencia en el Teams centro de administración, la forma en que asigne las direcciones o las cambie más adelante dependerá de su operador.

Para asignar números a las direcciones de emergencia, el operador implementará uno de los tres escenarios siguientes:

- El operador asigna direcciones de emergencia a los números de teléfono y le permite cambiarlas más adelante en el centro de administración de Teams.

- El operador no asigna direcciones y le permite asignar direcciones de emergencia a los números de teléfono del centro de administración de Teams.

- El operador asigna direcciones de emergencia a los números de teléfono y no le permite cambiarlas. En este escenario, deberá ponerse en contacto con su operador para realizar cambios en los números de teléfono y su dirección de emergencia asignada.

Para obtener más información sobre las llamadas de emergencia, consulte [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) y [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de Planes de llamadas a Conexión con operador

1. Póngase en contacto con su operador para transferir los números a Conexión con operador. Consulta [Microsoft 365 Conexión con operador directorio](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) para buscar el sitio web del operador.

2. Una vez que el operador complete la solicitud de portabilidad, puede anular la asignación de los números de teléfono del plan de llamadas de los usuarios y quitar la licencia del plan de llamadas. A continuación, el operador puede cargar los números en su inquilino.

3. Asigne números de Conexión con operador a los usuarios mediante el centro de administración de Teams o PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Enrutamiento directo a Conexión con operador

Para mover números de Enrutamiento directo a Conexión con operador, el número de Enrutamiento directo existente que su operador cargó en su inquilino debe quitarse del usuario al que está asignado. Después, después de migrar el número a Conexión con operador, puede volver a asignar el número al usuario. Para pasar del enrutamiento directo a Conexión con operador con números de teléfono locales o en línea, siga estos pasos:

>[!IMPORTANT]
> El número de teléfono estará fuera de servicio durante la migración, por lo que deberá coordinarse con su operador de Conexión con operador antes de empezar.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Paso 1: Quitar los números de enrutamiento directo existentes.

La forma de quitar los números de enrutamiento directo existentes depende de si el número está asignado de forma local o en línea. Para comprobarlo, ejecute el siguiente comando Teams módulo de PowerShell:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

Si `OnPremLineUri` se rellena con un número de teléfono E.164, el número de teléfono se asignó de forma local y se sincronizó con Office 365.
    
**Para quitar los números de enrutamiento directo asignados localmente,** ejecute el siguiente comando Skype Empresarial Server PowerShell:
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

La cantidad de tiempo que tarda en surtir efecto la eliminación depende de la configuración. Para comprobar si se quitó el número local y se han sincronizado los cambios, ejecute el siguiente comando Teams módulo de PowerShell: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Después de que los cambios se hayan sincronizado con Office 365 directorio en línea, el resultado esperado es: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **Para quitar los números de enrutamiento directo en línea existentes asignados en línea,** ejecute el siguiente comando Teams módulo de PowerShell:


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Quitar el número de teléfono puede tardar hasta 10 minutos. En raras ocasiones, pueden pasar hasta 24 horas. Para comprobar si se ha quitado el número de teléfono, ejecute el siguiente comando Teams módulo de PowerShell: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Paso 2: Quitar la directiva de enrutamiento de voz en línea asociada con el usuario

Una vez que el número esté sin asignar, quite la directiva de enrutamiento de voz en línea asociada con el usuario ejecutando el siguiente comando Teams módulo de PowerShell:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Paso 3: Adquirir números de teléfono

Ve al sitio web de tu operador para pedir y adquirir números de teléfono. Para buscar el sitio web de los operadores, consulte el [directorio de Microsoft 365 Conexión con operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

#### <a name="step-4---assign-phone-numbers"></a>Paso 4: Asignar números de teléfono

Una vez que el operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de > Teléfono de voz**. Asigne números de Conexión con operador a los usuarios mediante el centro de administración de Teams o PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

### <a name="assign-numbers"></a>Asignar números

Para obtener información sobre cómo asignar números de teléfono a los usuarios, vea [Asignar, cambiar o quitar un número de teléfono a un usuario](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>Administrar los operadores

En la pestaña **Mis operadores** , puede ver sus operadores y su estado y realizar los siguientes cambios en las selecciones:  

- Administrar los servicios del operador por país
- Suspender un operador
- Quitar un operador

> [!NOTE]
> Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o del país y ponerse en contacto con el operador para liberar los números.

## <a name="release-numbers"></a>Números de versión

Para liberar números de teléfono del centro de administración de Teams, vaya a la página **números de Teléfono** y seleccione un número.

- Si el número de teléfono no está asignado a un usuario, seleccione **Liberar**.

- Si el número de teléfono está asignado a un usuario, tendrá que anular la asignación del número. Seleccione **Editar** y, después, **Quitar usuario**. Después de guardar los cambios, selecciona **Liberar**.

## <a name="related-topics"></a>Temas relacionados

- [Planear Teams operadores automáticos y colas de llamadas](plan-auto-attendant-call-queue.md)
