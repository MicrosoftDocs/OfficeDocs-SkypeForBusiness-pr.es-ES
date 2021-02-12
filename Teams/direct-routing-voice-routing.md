---
title: Configurar el enrutamiento de voz para enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el enrutamiento de voz con enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530997"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurar el enrutamiento de voz para enrutamiento directo

En este artículo se describe cómo configurar el enrutamiento de voz para el enrutamiento directo de sistema telefónico.  Este es el paso 3 de los siguientes pasos para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar a los usuarios el enrutamiento directo, la voz y el correo de voz](direct-routing-enable-users.md)
- **Paso 3. Configurar el enrutamiento de** voz (en este artículo)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

## <a name="voice-routing-overview"></a>Información general sobre el enrutamiento de voz

Microsoft Phone System tiene un mecanismo de enrutamiento que permite que una llamada se envíe a un controlador de borde de sesión (SBC) específico en función de: 

- El patrón de número llamado 
- El patrón de número llamado y el usuario específico que realiza la llamada
 
Los SDC se pueden designar como activos y de copia de seguridad. Cuando el SBC que está configurado como activo no está disponible para una ruta de llamada específica, la llamada se enruta a una copia de seguridad SBC.
 
El enrutamiento de voz está basado en los siguientes elementos: 

- **Directiva de enrutamiento de** voz: contenedor para usos de RTC, que se puede asignar a un usuario o a varios usuarios. 

- **Usos de RTC:** contenedor para las rutas de voz y los usos de RTC, que se pueden compartir en diferentes directivas de enrutamiento de voz. 

- **Rutas de voz:** un patrón de números y un conjunto de puertas de enlace RTC en línea que se pueden usar para llamadas cuando el número de llamada coincida con el patrón.

-  Puerta de enlace RTC en línea: un puntero a un SBC que también almacena la configuración que se aplica cuando una llamada se hace a través del SBC, como reenvío de identidad profesional (PAI) o códecs preferidos. se pueden agregar a las rutas de voz.

## <a name="voice-routing-policy-considerations"></a>Consideraciones de directivas de enrutamiento de voz

Si un usuario tiene una licencia de plan de llamadas, las llamadas salientes de ese usuario se enruta automáticamente a través de la infraestructura RTC del plan de llamadas de Microsoft. Si configura y asigna una directiva de enrutamiento de voz en línea a un usuario del plan de llamadas, las llamadas salientes del usuario se comprobarán para determinar si el número marcado coincide con un patrón de número definido en la directiva de enrutamiento de voz en línea. Si hay una coincidencia, la llamada se enruta a través del tronco de enrutamiento directo. Si no hay ninguna coincidencia, la llamada se enruta a través de la infraestructura rtc del plan de llamadas.

> [!CAUTION]
> Si configura y aplica la directiva de enrutamiento de voz en línea global (predeterminada para toda la organización), todos los usuarios habilitados para voz de su organización heredarán esa directiva, lo que puede provocar que las llamadas RTC de usuarios del plan de llamadas se enruten sin darse cuenta a un tronco de enrutamiento directo. Si no desea que todos los usuarios usen la directiva global de enrutamiento de voz en línea, configure una directiva de enrutamiento de voz en línea personalizada y asígnela a usuarios individuales habilitados para voz.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Ejemplo 1: Enrutamiento de voz con un uso de RTC

El siguiente diagrama muestra dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.

**Flujo de llamadas 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si no sbc1.contoso.biz ni sbc2.contoso.biz disponibles, la llamada se descarta. 

**Flujo de llamadas 2 (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si no hay disponible SBC, se probará la ruta con una prioridad inferior (sbc3.contoso.biz y sbc4.contoso.biz). Si ninguno de los SBC está disponible, la llamada se descarta. 

![Muestra ejemplos de directivas de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueban de forma aleatoria los SBC de las rutas. Cuando dos SBC están configurados en una ruta, el tráfico de red debe ser enrutable entre SBC o multimedia no se establecerá en las transferencias, ya que es posible que la nueva invitación para la transferencia se envíe a otro SBC en la ruta.

  > [!NOTE]
  > A menos que el usuario también tenga una licencia de Microsoft Calling Plan, las llamadas a cualquier número excepto los números que coincidan con los patrones +1 425 XXX XX XX o +1 206 XXX XX XX en la configuración de ejemplo se descartan. Si el usuario tiene una licencia de plan de llamadas, la llamada se enruta automáticamente según las directivas del plan de llamadas de Microsoft. El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de Microsoft Calling Plan y no requiere configuración adicional de enrutamiento de llamadas.

En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de EE. UU. y Canadá (llamadas que van a llamar a patrón de números +1 XXX XXX XX XX).

![Muestra la directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

En el resto de llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Calling Plan), se usará la ruta automática. Si no hay nada que coincida con los patrones de números en las rutas de voz en línea creadas por el administrador, la llamada se enruta a través de Microsoft Calling Plan. Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay reglas que coincidan.

  > [!NOTE]
  > El valor de prioridad de la ruta "Otros +1" no importa en este caso porque solo hay una ruta que coincida con el patrón +1 XXX XXX XX XX. Si un usuario llama al +1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, la llamada se descarta.

En la tabla siguiente se resume la configuración mediante tres rutas de voz. En este ejemplo, las tres rutas forman parte del mismo uso de RTC, "EE. UU. y Canadá".  Todas las rutas están asociadas con el uso de RTC de "EE. UU. y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "Solo para ESTADOS UNIDOS".

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ee. UU. y Canadá|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números llamados +1 425 XXX XX o +1 206 XXX XX XX|
|Ee. UU. y Canadá|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de copia de seguridad para números llamados +1 425 XXX XX o +1 206 XXX XX XX|
|Ee. UU. y Canadá|"Otros +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Ruta para números llamados +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Ejemplo 1: Pasos de configuración

En el ejemplo siguiente se muestra cómo:

1. Cree un único uso de RTC.
2. Configure tres rutas de voz.
3. Cree una directiva de enrutamiento de voz.
4. Asigne la directiva a un usuario llamado Low.

Puede usar el Centro [de administración de Microsoft Teams](#admincenterexample1) o [PowerShell](#powershellexample1) para realizar estos pasos.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Paso 1: Crear el uso de RTC "EE. UU. y Canadá"

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, en la esquina superior derecha, seleccione Administrar registros  >  de uso **de RTC.**
2. Haga **clic en Agregar,** escriba **EE. UU. y Canadá** y, a continuación, haga clic en **Aplicar.**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)

En los pasos siguientes se describe cómo crear una ruta de voz. Siga estos pasos para crear las tres rutas de voz denominadas Redmond 1, Redmond 2 y Otros +1 para este ejemplo mediante la configuración descrita en la tabla anterior.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, después, seleccione  >  la **pestaña Rutas de** voz.
2. Haga **clic en** Agregar y, a continuación, escriba un nombre y una descripción para la ruta de voz.
3. Establezca la prioridad y especifique el patrón de número marcado.
4. Para inscribir un SBC con la ruta de voz, en los SBC inscritos **(opcional),** haga clic en Agregar SBC, seleccione los SBC que desea inscribir y, a continuación, haga clic en **Aplicar.**
5. Para agregar registros de uso de RTC, en Registros de uso de RTC **(opcional),** haga clic en Agregar uso de **RTC,** seleccione los registros RTC que desea agregar y, a continuación, haga clic en **Aplicar.**
6. Haga clic en **Guardar**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Paso 3: Crear una directiva de enrutamiento de voz denominada "Solo Estados Unidos" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las **directivas** de enrutamiento de voz y, a continuación, haga clic  >  en **Agregar.**
2. Escriba **US Only** como nombre y agregue una descripción.
3. En **Registros de uso de RTC,** haga clic en Agregar uso de RTC, seleccione el registro de uso de RTC "EE. UU. y Canadá" y, a continuación, haga clic en **Aplicar.** 
4. Haga clic en **Guardar**.

Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Low

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic **en Directivas** y, junto a **Directivas asignadas,** haga clic en **Editar.**
3. En **Directiva de enrutamiento de** voz, seleccione la directiva "Solo Estados Unidos" y, a continuación, haga clic en **Guardar.**

Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)

### <a name="using-powershell"></a>Con PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Paso 1: Crear el uso de RTC "EE. UU. y Canadá"

En una sesión remota de PowerShell en Skype Empresarial Online, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Compruebe que el uso se creó especificando:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Lo que devuelve una lista de nombres que pueden truncarse:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

En el ejemplo siguiente se muestra el resultado de ejecutar el comando PowerShell para mostrar nombres completos `(Get-CSOnlinePSTNUsage).usage` (no truncados):

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)

Para crear la ruta de "Redmond 1", en una sesión de PowerShell en Skype Empresarial Online, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Que devuelve:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

Para crear la ruta de Redmond 2, escribe:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para crear la ruta Otros +1, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Asegúrese de que la expresión regular del atributo NumberPattern es una expresión válida. Puede probarlo con este sitio web: [https://www.regexpal.com](https://www.regexpal.com)

En algunos casos, es necesario enrutar todas las llamadas al mismo SBC; use -NumberPattern ".*"

Enrutar todas las llamadas al mismo SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Compruebe que ha configurado correctamente la ruta ejecutando el comando `Get-CSOnlineVoiceRoute` de PowerShell con opciones como se muestra:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Lo que debería devolver:
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "Otros +1". 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Paso 3: Crear una directiva de enrutamiento de voz denominada "Solo Estados Unidos" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva

En una sesión de PowerShell en Skype Empresarial Online, escriba:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

El resultado se muestra en este ejemplo:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Low

En una sesión de PowerShell en Skype Empresarial Online, escriba:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide la asignación de directiva especificando este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

El comando devuelve lo siguiente:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Ejemplo 2: Enrutamiento de voz con varios usos de RTC

La directiva de enrutamiento de voz creada en el ejemplo 1 solo permite las llamadas a números de teléfono de Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.

En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "Sin restricciones". La directiva reutiliza el uso de RTC "EE. UU. y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "Internacional". Esta directiva desvía todas las demás llamadas a las sbc2.contoso.biz y sbc5.contoso.biz.

En los ejemplos que se muestran se asigna la directiva US Only al usuario Low y la directiva Sin restricciones al usuario John Protocol para que el enrutamiento se realice de la siguiente manera:

- Qué bajo: directiva de EE. UU. solo.  Las llamadas solo se permiten a números de EE. UU. y canadienses. Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC. Los números que no sean de EE. UU. no se enruta a menos que se asigne al usuario una licencia del plan de llamadas.

- John Bosques: directiva internacional.  Las llamadas se permiten a cualquier número. Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC. Los números que no sean de EE. UU. se enruta con sbc2.contoso.biz y sbc5.contoso.biz.

![Muestra la directiva de enrutamiento de voz asignada al usuario Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

En el resto de llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Calling Plan), se usa la ruta automática. Si no hay nada que coincida con los patrones de números de las rutas de voz en línea creadas por el administrador, la llamada se enruta con el plan de llamadas de Microsoft.  Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay reglas que coincidan.

![Muestra la directiva de enrutamiento de voz asignada al usuario JohnPecto](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

En la tabla siguiente se resumen las designaciones de uso y las rutas de voz "Sin restricciones" de la directiva de enrutamiento. 

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ee. UU. y Canadá|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números del destinatario +1 425 XXX XX XX o +1 206 XXX XX XX|
|Ee. UU. y Canadá|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de copia de seguridad para números del destinatario +1 425 XXX XX XX o +1 206 XXX XX XX|
|Ee. UU. y Canadá|"Otros +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Ruta para números de destinatario +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Ruta para cualquier patrón de números |

  > [!NOTE]
  > - El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental. Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, nunca se evalúan otros usos. El uso de RTC "Internacional" debe colocarse después del uso de RTC "EE. UU. y Canadá". Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Por ejemplo, para cambiar el orden de "EE. UU. y Canadá" primero e "Internacional" segundo al orden inverso ejecute:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La prioridad de las rutas de voz "Otros +1" e "Internacional" se asigna automáticamente. No importan tanto como tengan prioridades más bajas que "Redmond 1" y "Redmond 2".

## <a name="example-2-configuration-steps"></a>Ejemplo 2: Pasos de configuración

En el ejemplo siguiente se muestra cómo:

1. Cree un nuevo uso de RTC llamado Internacional.
2. Crea una nueva ruta de voz llamada Internacional.
3. Cree una directiva de enrutamiento de voz llamada Sin restricciones.
4. Asigne la directiva al usuario John Bosques.

Puede usar el Centro [de administración de Microsoft Teams](#admincenterexample2) o [PowerShell](#powershellexample2) para realizar estos pasos.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Paso 1: Crear el uso de RTC "Internacional"

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, en la esquina superior derecha, seleccione Administrar registros  >  de uso **de RTC.**
2. Haga **clic en Agregar,** escriba **Internacional** y, a continuación, haga clic **en Aplicar.**

#### <a name="step-2-create-the-international-voice-route"></a>Paso 2: Crear la ruta de voz "Internacional"

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, después, seleccione  >  la **pestaña Rutas de** voz.
2. Haga **clic en** Agregar, escriba "Internacional" como nombre y, a continuación, agregue la descripción.
3. Establezca la prioridad en 4 y, a continuación, establezca el patrón de números marcados en \d+.
4. En **CCSS inscritos (opcional),** haga clic en Agregar OSN, seleccione sbc2.contoso.biz y sbc5.contoso.biz y, a continuación, haga clic en **Aplicar.**
5. En Registros de uso de RTC **(opcional),** haga clic en Agregar uso de **RTC,** seleccione el registro de uso de RTC "Internacional" y, a continuación, haga clic en **Aplicar.**
6. Haga clic en **Guardar**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones" y agregar los usos de RTC "EE. UU. y Canadá" e "Internacional" a la directiva

El uso de RTC "EE. UU. y Canadá" se reutiliza en esta directiva de enrutamiento de voz para conservar la administración especial para las llamadas al número "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las **directivas** de enrutamiento de voz y, a continuación, haga clic  >  en **Agregar.**
2. Escriba **Sin restricciones** como nombre y agregue una descripción.
3. En **Registros de uso** de RTC, haga clic en Agregar uso de RTC, seleccione el registro de uso de RTC "EE. UU. y Canadá" y, a continuación, seleccione el registro de uso de RTC "Internacional".  Haga clic en **Aplicar**.

    Anote el orden de los usos de RTC:

    - Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en este ejemplo, la llamada sigue la ruta establecida en "EE. UU. y Canadá" uso y se aplica la lógica de enrutamiento especial. Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.

    - Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.

4. Haga clic en **Guardar**.

Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado John Noé

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic **en Directivas** y, junto a **Directivas asignadas,** haga clic en **Editar.**
3. En **Directiva de enrutamiento de** voz, seleccione la directiva "Sin restricciones" y haga clic en **Guardar.**

El resultado es que la directiva de voz aplicada a las llamadas de John John Se ha restringido y seguirá la lógica del enrutamiento de llamadas disponible para llamadas estadounidenses, canadá e internacionales.

### <a name="using-powershell"></a>Con PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Paso 1: Crear el uso de RTC "Internacional"

En una sesión remota de PowerShell en Skype Empresarial Online, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Paso 2: Crear una nueva ruta de voz denominada "Internacional"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Que devuelve:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones"

El uso de RTC "Redmond 1" y "Redmond" se reutilizan en esta directiva de enrutamiento de voz para conservar la administración especial para las llamadas al número "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Anote el orden de los usos de RTC:

  - Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue la ruta establecida en "EE. UU. y Canadá" uso y se aplica la lógica de enrutamiento especial. Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.

  - Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento. Escriba el comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Que devuelve:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Paso 4: Asignar la directiva de enrutamiento de voz al usuario llamado John Seleán

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Después, compruebe la tarea con el comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Que devuelve:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

El resultado es que la directiva de voz aplicada a las llamadas de John John Se ha restringido y seguirá la lógica del enrutamiento de llamadas disponible para llamadas estadounidenses, canadá e internacionales.

## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
