---
title: 'Lync Server 2013: probar el inicio de sesión de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Probar el inicio de sesión de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de comprobación</p></td>
<td><p>Diario</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsPhoneBootstrap. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsPhoneBootstrap permite a los administradores comprobar que un usuario determinado (con el número de teléfono y el PIN que se le ha asignado) puede iniciar sesión en el sistema desde un dispositivo compatible con Lync 2013 Phone Edition. (En realidad, no se necesita ningún dispositivo para ejecutar la prueba).

Para que Test-CsPhoneBootstrap pueda realizar su comprobación, el grupo de registradores que hospeda la cuenta de usuario que se está probando debe ser detectable con DHCP. Para determinar si un registrador se detecta de esta manera, use el cmdlet Get-CsRegistrarConfiguration y compruebe el valor de la propiedad EnableDHCPServer. Si esta propiedad se establece en false, debe usar Set-CsRegistrarConfiguration para establecer el valor de la propiedad en true y hacer que el registrador sea detectable mediante DHCP. Esto también se puede hacer con el servidor DHCP de empresa y configurar las opciones específicas de Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsPhoneBootstrap, debe proporcionar, como mínimo, el número de teléfono y el número de identificación personal del cliente (PIN) para un usuario válido de Lync Server. Por ejemplo, este comando comprueba la capacidad de inicio de sesión del usuario que tiene el número de teléfono 12065551219 y el PIN 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Para una comprobación más completa, también puede incluir la dirección SIP del usuario. En ese caso, el número de teléfono, el PIN del cliente y la dirección SIP deben ser válidos para que la prueba se realice correctamente:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado pudo conectar con Lync Server, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. SVC

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.3981276

Error

Diagnóstico

Si el usuario especificado no ha podido establecer una conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:04.1993845

Error: ERROR: no se recibió ninguna respuesta para el servicio de vales Web.

Diagnóstico

La salida anterior indica que se produjo un error en la prueba porque el servicio de vale web no respondió. Esto puede deberse a un problema con el servicio, o puede deberse a la dirección SIP, el número de teléfono o el PIN del cliente que se ha pasado a test-CsPhoneBootstrap. Puede comprobar la dirección SIP y el número de teléfono del usuario con un comando similar a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Además, puede comprobar que el usuario tiene un PIN válido con un comando de la siguiente manera:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Si test-CsPhoneBootstrap produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Cuando se incluye el parámetro verbose, test-CsPhoneBootstrap devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, a continuación se muestra una parte de la salida de un inicio de sesión incorrecto, una sesión en la que se incluyó un PIN incorrecto:

Uso de la autenticación de\\pin con extensión de teléfono: 12065551219 PIN: 0712

No se pudo obtener el vale Web

SILLA

\-La URL del servicio web es válida y los servicios web son funcionales

\-Si usa PhoneNo\\PIN para autenticarse, asegúrese de que coinciden con el URI de usuario

\-Si se usa\\la autenticación Kerberos NTLM, asegúrese de que ha proporcionado credenciales válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsPhoneBootstrap podría fallar:

  - Es posible que haya especificado una dirección SIP que no sea válida. Puede comprobar que la dirección SIP es correcta usando un comando como el siguiente:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Es posible que haya especificado un PIN que no es válido. Aunque no puede recuperar el número PIN del usuario, puede comprobar que al menos el usuario tiene un número PIN mediante un comando similar al siguiente:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Puede que haya especificado un número de teléfono que no es válido. Puede comprobar el teléfono de un usuario con un comando similar al siguiente:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - El grupo de registrador no está habilitado para DHCP. Para determinar si el grupo de registrador está habilitado para DHCP, ejecute el cmdlet Get-CsRegistrarConfiguration y compruebe el valor de la propiedad EnableDHCPServer. Por ejemplo:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

