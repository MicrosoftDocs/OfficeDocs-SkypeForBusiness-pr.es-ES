---
title: Configurar el enrutamiento de voz para el enrutamiento directo
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
description: Obtenga información sobre cómo configurar el enrutamiento de voz con el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 37343ad177e3408f94103296509e4b9bfc8ea759
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359416"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurar el enrutamiento de voz para el enrutamiento directo

En este artículo se describe cómo configurar el enrutamiento de voz para el enrutamiento directo de un sistema telefónico.  Este es el paso 3 de los pasos siguientes para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- Paso 2. [Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz](direct-routing-enable-users.md)
- **Paso 3. Configurar el enrutamiento de voz** (este artículo)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Introducción al enrutamiento de voz

Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un controlador de borde de sesión (SBC) específico en función de: 

- El patrón de número al que se llama 
- El patrón de número al que se llama y el usuario específico que realiza la llamada
 
SBCs puede designarse como activo y como backup. Cuando el SBC configurado como activo no está disponible para una ruta de llamada específica, la llamada se redirigirá a un SBC de copia de seguridad.
 
El enrutamiento de voz consta de los siguientes elementos: 

- **Directiva de enrutamiento de voz** : contenedor de uso de RTC, que se puede asignar a un usuario o a varios usuarios. 

- **Usos de RTC** : un contenedor de rutas de voz y usos de RTC, que se pueden compartir en diferentes directivas de enrutamiento de voz. 

- **Rutas de voz** : un patrón de número y un conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón.

- **Puerta de enlace RTC en línea** : puntero a un SBC que también almacena la configuración que se aplica cuando una llamada se coloca a través de SBC, como la identidad de aserción de P (PAI) o los códecs preferidos. se puede Agregar a las rutas de voz.

## <a name="voice-routing-policy-considerations"></a>Consideraciones de directiva de enrutamiento de voz

Si un usuario tiene una licencia de plan de llamadas, las llamadas salientes de ese usuario se enrutan automáticamente a través de la infraestructura RTC del plan de llamadas de Microsoft. Si configura y asigna una directiva de enrutamiento de voz en línea a un usuario del plan de llamadas, se comprobarán las llamadas salientes de ese usuario para determinar si el número marcado coincide con un patrón de número definido en la Directiva de enrutamiento de voz en línea. Si hay una coincidencia, la llamada se dirige a través del tronco de enrutamiento directo. Si no hay ninguna coincidencia, la llamada se dirige a través de la infraestructura RTC del plan de llamadas.

> [!CAUTION]
> Si configura y aplica la Directiva de enrutamiento de voz en línea global (predeterminada para toda la organización), todos los usuarios habilitados para voz de la organización heredarán esa Directiva, lo que puede provocar que las llamadas RTC se dirijan de forma inadvertida a un tronco de enrutamiento directo. Si no desea que todos los usuarios usen la Directiva de enrutamiento de voz en línea global, configure una directiva de enrutamiento de voz en línea personalizada y asígnela a usuarios habilitados para voz.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Ejemplo 1: enrutamiento de voz con un uso de RTC

En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.

**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe. 

**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz. Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz). Si ninguno de los SBCs está disponible, la llamada se corta. 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.

  > [!NOTE]
  > A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan. Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft. El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.

En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números canadienses y de Estados Unidos (llamadas que van al patrón de números llamado + 1 XXX XXX XX XX).

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática. Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se dirige a través del plan de llamadas de Microsoft. Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay disponibles reglas coincidentes.

  > [!NOTE]
  > El valor de prioridad para la ruta "otros + 1" no importa en este caso porque hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX. Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.

En la tabla siguiente se resume la configuración mediante tres rutas de voz. En este ejemplo, las tres rutas forman parte del mismo uso de la RTC, "Estados Unidos y Canadá".  Todas las rutas se asocian con el uso de RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para Estados Unidos".

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos y Canadá|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Estados Unidos y Canadá|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX|
|Estados Unidos y Canadá|"Otros + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Ejemplo 1: pasos de configuración

En el ejemplo siguiente se muestra cómo:

1. Crear un único uso de RTC.
2. Configurar tres rutas de voz.
3. Crear una directiva de enrutamiento de voz.
4. Asigne la Directiva a un usuario denominado Spencer Low.

Puede usar el [centro de administración de Microsoft Teams](#admincenterexample1) o [PowerShell](#powershellexample1) para realizar estos pasos.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Paso 1: crear el uso de la RTC "Estados Unidos y Canadá"

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo**y, a continuación, en la esquina superior derecha, seleccione **administrar registros de uso de RTC**.
2. Haga clic en **Agregar**, escriba **Estados Unidos y Canadá**y, a continuación, haga clic en **aplicar**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Paso 2: crear tres rutas de voz (Redmond 1, Redmond 2 y otros + 1)

Los pasos siguientes describen cómo crear una ruta de voz. Siga estos pasos para crear las tres rutas de voz llamada Redmond 1, Redmond 2 y otro + 1 para este ejemplo con la configuración descrita en la tabla anterior.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo**y, a continuación, seleccione la pestaña **rutas de voz** .
2. Haga clic en **Agregar**y, a continuación, escriba un nombre y una descripción para la ruta de voz.
3. Establezca la prioridad y especifique el patrón de número marcado.
4. Para inscribir un SBC con la ruta de voz, en **SBCS inscrito (opcional)**, haga clic en **Agregar SBCS**, seleccione el SBCS que desea inscribir y, a continuación, haga clic en **aplicar**.
5. Para agregar registros de uso de RTC, en **registros de uso de RTC (opcional)**, haga clic en **Agregar uso de RTC**, seleccione los registros RTC que desea agregar y, a continuación, haga clic en **aplicar**.
6. Haga clic en **Guardar **.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Paso 3: crear una directiva de enrutamiento de voz denominada "solo para EE. UU." y agregar el uso de RTC "Estados Unidos y Canadá" a la Directiva

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de enrutamiento de voz de **voz**  >  **Voice routing policies**y haga clic en **Agregar**.
2. Escriba **solo** el nombre del contacto y agregue una descripción.
3. En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "Estados Unidos y Canadá" y, a continuación, haga clic en **aplicar**.
4. Haga clic en **Guardar **.

Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado Spencer Low

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de enrutamiento de voz**, seleccione la Directiva "solo para Estados Unidos" y, a continuación, haga clic en **Guardar**.

Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Con PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Paso 1: crear el uso de la RTC "Estados Unidos y Canadá"

En una sesión de PowerShell remoto en Skype empresarial online, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Para comprobar que el uso se ha creado, escriba:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Que devuelve una lista de los nombres que se pueden truncar:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

En el siguiente ejemplo se muestra el resultado de ejecutar el `(Get-CSOnlinePSTNUsage).usage` comando PowerShell para mostrar nombres completos (no truncado):

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Paso 2: crear tres rutas de voz (Redmond 1, Redmond 2 y otros + 1)

Para crear la ruta de "Redmond 1", en una sesión de PowerShell en Skype empresarial online, escriba:

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

Para crear la ruta de Redmond 2, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para crear la ruta otra + 1, escriba:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida. Puede probarla con este sitio web: [https://www.regexpal.com](https://www.regexpal.com)

En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". *"

Enrutar todas las llamadas al mismo SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Compruebe que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Que debería devolver:
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

En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1". 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Paso 3: crear una directiva de enrutamiento de voz denominada "solo para EE. UU." y agregar el uso de RTC "Estados Unidos y Canadá" a la Directiva

En una sesión de PowerShell en Skype empresarial online, escriba:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado Spencer Low

En una sesión de PowerShell en Skype empresarial online, escriba:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide la asignación de directiva escribiendo este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

El comando devuelve lo siguiente:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Ejemplo 2: enrutamiento de voz con varios usos de RTC

La Directiva de enrutamiento de voz creada en el ejemplo 1 solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.

En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones". La Directiva reutiliza el uso de RTC "Estados Unidos y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "internacional". Esta directiva dirige todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs.

Los ejemplos que se muestran asignan la Directiva solo de Estados Unidos a User Spencer Low y la Directiva sin restricciones para el usuario John Woods, de modo que el enrutamiento se produce de la siguiente manera:

- Spencer solamente política de Estados Unidos.  Las llamadas solo se permiten a números de Estados Unidos y Canadá. Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs. Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.

- John Woods: política internacional.  Las llamadas pueden realizarse a cualquier número. Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs. Los números que no sean de Estados Unidos se enrutarán mediante sbc2.contoso.biz y sbc5.contoso.biz.

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática. Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se redirige a través del plan de llamadas de Microsoft.  Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones". 

|**Uso de RTC**|**Ruta de voz**|**Patrón de números**|**Prioridad**|**SBC**|**Descripción**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos y Canadá|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Estados Unidos y Canadá|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Estados Unidos y Canadá|"Otros + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Ruta para cualquier patrón de números |

  > [!NOTE]
  > - El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental. Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos. El uso de RTC "internacional" debe colocarse después del uso de RTC "Estados Unidos y Canadá". Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente. No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".

## <a name="example-2-configuration-steps"></a>Ejemplo 2: pasos de configuración

En el ejemplo siguiente se muestra cómo:

1. Cree un nuevo uso de RTC denominado internacional.
2. Cree una nueva ruta de voz denominada internacional.
3. Crear una directiva de enrutamiento de voz llamada sin restricciones.
4. Asigne la Directiva al usuario John Woods.

Puede usar el [centro de administración de Microsoft Teams](#admincenterexample2) o [PowerShell](#powershellexample2) para realizar estos pasos.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Paso 1: crear el uso de RTC "internacional"

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo**y, a continuación, en la esquina superior derecha, seleccione **administrar registros de uso de RTC**.
2. Haga clic en **Agregar**, escriba **internacional**y, a continuación, haga clic en **aplicar**.

#### <a name="step-2-create-the-international-voice-route"></a>Paso 2: crear la ruta de voz "internacional"

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo**y, a continuación, seleccione la pestaña **rutas de voz** .
2. Haga clic en **Agregar**, escriba "internacional" como nombre y, a continuación, agregue la descripción.
3. Establezca la prioridad en 4 y, a continuación, establezca el patrón de número marcado como \d +.
4. En **SBCS inscrito (opcional)**, haga clic en **Agregar SBCs**, seleccione sbc2.contoso.BIZ y sbc5.contoso.BIZ y, a continuación, haga clic en **aplicar**.
5. En **registros de uso de RTC (opcional)**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "internacional" y, a continuación, haga clic en **aplicar**.
6. Haga clic en **Guardar **.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Paso 3: crear una directiva de enrutamiento de voz denominada "sin restricciones" y agregar los usos de "Estados Unidos y Canadá" y "internacional" a la Directiva

El uso de la RTC "Estados Unidos y Canadá" se reutiliza en esta directiva de enrutamiento de voz para mantener el control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de enrutamiento de voz de **voz**  >  **Voice routing policies**y haga clic en **Agregar**.
2. Escriba **ninguna restricción** como nombre y agregue una descripción.
3. En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "Estados Unidos y Canadá" y, a continuación, seleccione el registro de uso de RTC "internacional". Haga clic en **Aplicar**.

    Tome nota del orden de uso de RTC:

    - Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados, como en este ejemplo, la llamada sigue la ruta establecida en el uso de "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial. Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.

    - Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.

4. Haga clic en **Guardar **.

Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado John Woods

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de enrutamiento de voz**, seleccione la Directiva "sin restricciones" y, a continuación, haga clic en **Guardar**.

El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones y seguirá la lógica del enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.

### <a name="using-powershell"></a>Con PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Paso 1: crear el uso de RTC "internacional"

En una sesión de PowerShell remoto en Skype empresarial online, escriba:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Paso 2: crear una nueva ruta de voz denominada "internacional"

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Paso 3: crear una directiva de enrutamiento de voz denominada "sin restricciones"

El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Tome nota del orden de uso de RTC:

  - Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue el conjunto de rutas en "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial. Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.

  - Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento. Escribe el comando:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Paso 4: asignar la Directiva de enrutamiento de voz al usuario denominado John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

A continuación, verifique la asignación con el comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Que devuelve:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
