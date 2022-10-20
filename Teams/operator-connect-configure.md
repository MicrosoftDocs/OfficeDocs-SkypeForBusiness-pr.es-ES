---
title: Configurar Operador Conectar
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtén más información sobre cómo configurar Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03fa1900986b12925e2f611e2d6553d9e5d627f8
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613872"
---
# <a name="configure-operator-connect"></a>Configurar Operador Conectar

En este artículo se describe cómo configurar Operator Connect. Antes de configurar Operador Connect, asegúrese de leer [Plan para operador conectarse](operator-connect-plan.md) para obtener información sobre los requisitos previos y la licencia.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el Centro de administración de Teams. En el panel de navegación izquierdo, vaya a **Operadores de > de voz**.

Para habilitar un operador:

1. **Elige un operador.** En la pestaña **Todos los operadores** , filtre los operadores disponibles por región o servicio para encontrar el operador adecuado para sus necesidades de voz. A continuación, selecciona el operador que quieras habilitar.  

2. **Seleccione países.** En **Configuración del operador**, selecciona los países que quieras habilitar con el operador seleccionado.

3. **Proporcionar información de contacto** Tu información de contacto, incluyendo tu nombre completo y dirección de correo electrónico, se compartirá automáticamente con tu operador. Puede cambiar esta información más adelante. Además, tendrás que proporcionar el tamaño de la empresa y tendrás la opción de proporcionar tu número de teléfono. Los operadores usarán esta información para ponerse en contacto con usted con más detalles sobre Operator Connect.

4. Acepta el aviso de transferencia de datos.

5. **Agrega tu operador.** Selecciona **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

La manera de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo los números existentes de los planes de llamadas de Microsoft o del enrutamiento directo.

- Si necesita adquirir números de teléfono para nuevos usuarios, consulte [Adquirir números para nuevos usuarios de Teams](#acquire-numbers-for-new-teams-users).

- Si desea mover números existentes de Planes de llamada a Operador Conectar, consulte [Mover números de Planes de llamada a Operador Conectar](#move-numbers-from-calling-plans-to-operator-connect).

- Si desea mover los números existentes de Enrutamiento directo a Conexión de operador, vea [Mover números de Enrutamiento directo a Conexión de operador](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="assign-numberes-to-emergency-addresses"></a>Asignar números a direcciones de emergencia

La dirección de emergencia es una ubicación estática asociada a un número. Una vez creadas las direcciones de emergencia en el Centro de administración de Teams, la forma de asignarlas o cambiarlas más adelante dependerá de su operador.

Para asignar números a las direcciones de emergencia, el operador implementará uno de los tres escenarios siguientes:

- El operador asigna direcciones de emergencia a los números de teléfono y le permite cambiarlas más adelante en el Centro de administración de Teams.

- El operador no asigna direcciones y le permite asignar direcciones de emergencia a los números de teléfono del centro de administración de Teams.

- El operador asigna direcciones de emergencia a los números de teléfono y no le permite cambiarlas. En este escenario, deberá ponerse en contacto con su operador para realizar cambios en los números de teléfono y su dirección de emergencia asignada.

Para obtener más información sobre las llamadas de emergencia, consulte [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) y [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos usuarios de Teams

Para adquirir números para nuevos usuarios de Teams, siga estos pasos:

1. **Asignar una licencia de Sistema telefónico.** Puede asignar una licencia de Sistema telefónico a los usuarios desde la Centro de administración de Microsoft 365 o mediante PowerShell. Para obtener más información, consulte [Asignar licencias de complementos de Teams a usuarios](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Los usuarios a los que se les asignarán números de teléfono adquiridos con Operator Connect deben estar en el modo TeamsOnly. Si su organización está en modo TeamsOnly, todos los usuarios se encuentran en el modo TeamsOnly. Para comprobarlo, en el Centro de administración de Teams, vaya a **Teams > configuración de actualización de Teams**. Si su organización está en modo Islas, compruebe si determinados usuarios están en modo TeamsOnly. Vaya a **Usuarios** y seleccione una cuenta de usuario. En la pestaña **Cuenta** , en **Actualización de Teams,** el modo de coexistencia debe establecerse en "TeamsOnly".

3. **Adquirir números.** Ve al sitio web de tu operador para pedir y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, ve al [directorio Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

4. **Asignar números.** Una vez que el operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. Asigne números a los usuarios desde el Centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

> [!NOTE]
> Además de [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md), puede obtener números de teléfono gratuitos o de pago para servicios como Audioconferencia (para puentes de conferencia), Operadores automáticos y Colas de llamadas (también denominados números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede administrar cientos de llamadas simultáneamente, mientras que el número de teléfono de un usuario solo puede atender algunas llamadas simultáneamente. Para obtener números de servicio, ponte en contacto con tu operador.

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de Planes de llamadas a Operador Connect

1. Ponte en contacto con tu operador para transferir tus números al operador Conectar. Consulta directorio [Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) para buscar el sitio web de tu operador.

2. Una vez que el operador complete la solicitud de portabilidad, el operador cargará los números en su inquilino.

3. Asigne números de Operador Conectar a usuarios mediante el Centro de administración de Teams o PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Enrutamiento directo a Conexión de operadores

Para pasar de Enrutamiento directo a Conexión de operadores con números de teléfono locales o en línea, siga estos pasos:

#### <a name="step-1---identify-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Paso 1: identifique si los números de enrutamiento directo existentes están asignados en línea o de forma local.

Compruebe que el usuario tiene asignado un número de enrutamiento directo ejecutando el comando Módulo de PowerShell de Teams:

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

Compruebe que `NumberType` es DirectRouting.

La forma de quitar los números de enrutamiento directo existentes depende de si el número está asignado de forma local o en línea. Para comprobarlo, ejecute el siguiente comando del módulo de PowerShell de Teams:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

Si `OnPremLineUri` se rellena con un número de teléfono E.164, el número de teléfono se asignó de forma local y se sincronizó con Microsoft 365.

**Para migrar los números de enrutamiento directo existentes asignados en línea al operador Conectar**, póngase en contacto con su operador. Para buscar el sitio web de tu operador, consulta directorio [Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). En la fecha y hora acordadas, el operador migrará los números de Enrutamiento directo a Operador Conectar.

**Para migrar los números de enrutamiento directo asignados localmente a Operator Connect**, ejecute el siguiente comando Skype Empresarial Server PowerShell:
>[!IMPORTANT]
> El número de teléfono estará fuera de servicio durante la migración, por lo que debes coordinarlo con el operador Connect del operador antes de empezar.

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

La cantidad de tiempo que tarda en surtir efecto la eliminación depende de la configuración. Para comprobar si se ha quitado el número local y los cambios se han sincronizado desde el entorno local a Microsoft 365, ejecute el siguiente comando módulo de PowerShell de Teams: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Después de que los cambios se hayan sincronizado con el directorio en línea de Microsoft 365, el resultado esperado es: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```




```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Quitar el número de teléfono puede tardar hasta 10 minutos. En raras ocasiones, pueden pasar hasta 24 horas. Para comprobar si se ha quitado el número de teléfono, ejecute el siguiente comando del módulo de PowerShell de Teams: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Paso 2: Quitar la directiva de enrutamiento de voz en línea asociada con el usuario

Una vez que el número esté sin asignar, quite la directiva de enrutamiento de voz en línea asociada con el usuario ejecutando el siguiente comando módulo de PowerShell de Teams:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Paso 3: Adquirir números de teléfono

Ve al sitio web de tu operador para pedir y adquirir números de teléfono. Para encontrar el sitio web de los operadores, consulta el [directorio Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

#### <a name="step-4---assign-phone-numbers"></a>Paso 4: Asignar números de teléfono

Una vez que el operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. Asigne números de Operador Conectar a usuarios mediante el Centro de administración de Teams o PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

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

Para liberar números de teléfono desde el Centro de administración de Teams, vaya a la página **Números** de teléfono y seleccione un número.

- Si el número de teléfono no está asignado a un usuario, seleccione **Liberar**.

- Si el número de teléfono está asignado a un usuario, tendrá que anular la asignación del número. Seleccione **Editar** y, después, **Quitar usuario**. Después de guardar los cambios, selecciona **Liberar**.

## <a name="related-topics"></a>Temas relacionados

- [Planear operadores automáticos y colas de llamadas de Teams](plan-auto-attendant-call-queue.md)
