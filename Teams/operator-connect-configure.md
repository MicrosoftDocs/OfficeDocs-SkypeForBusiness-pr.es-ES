---
title: Configurar operador Conectar
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
description: Obtenga más información sobre cómo configurar operador Conectar.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa31a954bb36369417f408734fa3b1622e101e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384168"
---
# <a name="configure-operator-connect"></a>Configurar operador Conectar

En este artículo se describe cómo configurar operador Conectar. Antes de configurar Conectar operador, asegúrese de leer Plan para operadores [Conectar](operator-connect-plan.md) información sobre requisitos previos y licencias.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el centro Teams administración. En el panel de navegación izquierdo, vaya **a Operadores de > voz**.

Para habilitar un operador:

1. **Elija un operador.** En la **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de voz. A continuación, seleccione el operador que desea habilitar.  

2. **Seleccione países.** En **Configuración del operador**, seleccione los países que desea habilitar con el operador seleccionado.

3. **Proporcionar información de contacto** La información de contacto, incluido su nombre completo y su dirección de correo electrónico, se compartirá automáticamente con su operador. Puede cambiar esta información más adelante. Además, deberá proporcionar el tamaño de la empresa y tendrá la opción de proporcionar su número de teléfono. Los operadores usarán esta información para ponerse en contacto con usted para obtener más información sobre Conectar.

4. Aceptar el aviso de transferencia de datos.

5. **Agregue el operador.** Seleccione **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

La forma de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo números existentes desde Planes de llamadas de Microsoft o Enrutamiento directo.

- Si necesita adquirir números de teléfono para nuevos usuarios, vea [Adquirir números para nuevos Teams usuarios](#acquire-numbers-for-new-teams-users).

- Si desea mover números existentes de planes de llamadas a operador Conectar, vea Mover números de planes de llamadas [a operador Conectar](#move-numbers-from-calling-plans-to-operator-connect).

- Si desea mover números existentes de Enrutamiento directo a Operador Conectar, vea Mover números de enrutamiento directo [a operador Conectar](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos Teams usuarios

Para adquirir números para nuevos Teams usuarios, siga estos pasos:

1. **Asigne una Sistema telefónico licencia.** Puede asignar una licencia Sistema telefónico a los usuarios desde el Centro de administración de Microsoft 365 o con PowerShell. Para obtener más información, vea [Asignar Teams de complementos a los usuarios](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Los usuarios a los que se asignarán números de teléfono adquiridos Conectar operador deben estar en modo TeamsOnly. Si su organización está en modo TeamsOnly, todos los usuarios están en modo TeamsOnly. Para comprobarlo, en el Teams de administración, vaya a Teams > Teams **configuración de actualización**. Si su organización está en modo Islas, compruebe si determinados usuarios están en modo TeamsOnly. Vaya a **Usuarios** y seleccione una cuenta de usuario. En la **pestaña Cuenta**, en **Teams actualización,** el modo de coexistencia debe establecerse en "TeamsOnly".

3. **Adquirir números.** Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vaya al Microsoft 365 [de Conectar operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.

4. **Asignar números.** Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el centro Teams administración yendo **a Números de > Teléfono voz**. Asigne números a los usuarios desde el Teams de administración o mediante PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

> [!NOTE]
> Además de obtener números de teléfono para los  [usuarios, puede](getting-phone-numbers-for-your-users.md) obtener números de teléfono gratuitos o de pago para servicios como Audioconferencia (para puentes de conferencia), Operadores automáticos y Colas de llamadas (también denominados números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede controlar cientos de llamadas simultáneamente, mientras que el número de teléfono de un usuario solo puede controlar algunas llamadas simultáneamente. Para obtener números de servicio, póngase en contacto con su operador.

### <a name="emergency-addresses"></a>Direcciones de emergencia

La dirección de emergencia es una ubicación estática asociada a un número. Una vez que cree direcciones de emergencia en el centro de administración de Teams, la forma en que asigne las direcciones o las cambie más adelante dependerá de su operador.

Para asignar números a direcciones de emergencia, el operador implementará uno de tres escenarios:

- El operador asigna direcciones de emergencia a los números de teléfono y le permite cambiarlas más adelante en el centro Teams administración.

- El operador no asigna direcciones y le permite asignar direcciones de emergencia a los números de teléfono en el Teams de administración.

- El operador asigna direcciones de emergencia a los números de teléfono y no le permite cambiarlas. En este escenario, tendrá que ponerse en contacto con su operador para realizar cambios en los números de teléfono y su dirección de emergencia asignada.

Para obtener más información sobre las llamadas de emergencia, vea [Administrar llamadas de](what-are-emergency-locations-addresses-and-call-routing.md) emergencia y [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de planes de llamadas a operador Conectar

1. Póngase en contacto con su operador para portabilidad de los números a Operador Conectar. Consulte [Microsoft 365 operador Conectar directorio](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) para buscar el sitio web del operador.

2. Después de que el operador complete el pedido de porte, puede quitar los números de teléfono del Plan de llamadas de los usuarios y quitar la licencia del plan de llamadas. A continuación, el operador puede cargar los números en el espacio empresarial.

3. Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Enrutamiento directo a Operador Conectar

Para mover números de enrutamiento directo a operador Conectar, el número de enrutamiento directo existente que el operador carizó al inquilino debe quitarse del usuario al que está asignado. Después, después de migrar el número a Operador Conectar, puede volver a asignar el número al usuario. Para pasar de enrutamiento directo a operador Conectar con números de teléfono locales o en línea, siga estos pasos:

>[!IMPORTANT]
> El número de teléfono estará fuera de servicio durante la migración, así que coordine con su operador Conectar operador antes de empezar.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Paso 1: quitar los números de enrutamiento directo existentes.

La forma de quitar los números de enrutamiento directo existentes depende de si el número se asigna local o en línea. Para comprobarlo, ejecute el siguiente comando:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

Si `OnPremLineUriManuallySet` se establece en y `LineUri` `False` se rellena con un número de teléfono E.164, el número de teléfono se asignó localmente y se sincronizó a Office 365.
    
**Para quitar los números de enrutamiento directo asignados localmente,** ejecute el siguiente comando:
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

La cantidad de tiempo necesario para que la eliminación suba a efecto depende de la configuración. Para comprobar si se ha quitado el número local y se han sincronizado los cambios, ejecute el siguiente comando de PowerShell: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
Después de que los cambios se sincronicen Office 365 en línea, el resultado esperado es: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **Para quitar los números de enrutamiento directo en línea existentes que se asignan en línea,** ejecute el siguiente comando de PowerShell:


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Quitar el número de teléfono puede tardar hasta 10 minutos. En raras ocasiones, puede tardar hasta 24 horas. Para comprobar si se ha quitado el número local y se han sincronizado los cambios, ejecute el siguiente comando de PowerShell: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Paso 2: Quitar la directiva de enrutamiento de voz en línea asociada con el usuario

Una vez que el número esté sinsignar, quite la directiva de enrutamiento de voz en línea asociada con el usuario ejecutando el siguiente comando de PowerShell:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Paso 3: Adquirir números de teléfono

Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para buscar el sitio web de operadores, vea el [Microsoft 365 de Conectar operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Tendrá que proporcionar su id. de inquilino. Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.

#### <a name="step-4---assign-phone-numbers"></a>Paso 4: Asignar números de teléfono

Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el centro Teams administración yendo **a Números de > Teléfono voz**. Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell. Para obtener más información, vea [Asignar números](#assign-numbers).

### <a name="assign-numbers"></a>Asignar números

Para obtener información sobre cómo asignar números de teléfono a los usuarios, vea Asignar, cambiar o [quitar un número de teléfono para un usuario](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>Administrar los operadores

Desde la **pestaña Mis operadores** , puede ver los operadores y su estado y realizar los siguientes cambios en las selecciones:  

- Administrar servicios de operadores por país
- Suspender un operador
- Quitar un operador

> [!NOTE]
> Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o el país y ponerse en contacto con el operador para liberar los números.

## <a name="release-numbers"></a>Números de versión

Para liberar números de teléfono desde el Teams de administración, vaya a la **página Teléfono números de** teléfono y seleccione un número.

- Si el número de teléfono no está asignado a un usuario, seleccione **Liberar**.

- Si el número de teléfono está asignado a un usuario, deberá desasign el número. Seleccione **Editar** y, a continuación **, Quitar usuario**. Después de guardar los cambios, seleccione **Liberar**.

## <a name="related-topics"></a>Temas relacionados

- [Planear Teams operadores automáticos y colas de llamadas](plan-auto-attendant-call-queue.md)
