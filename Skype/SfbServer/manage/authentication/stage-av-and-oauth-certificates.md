---
title: Realizar copia intermedia de certificados AV y OAuth en Skype Empresarial Server 2015 usando -Roll en Set-CsCertificate
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumen: Fase AV OAuth certificados y de Skype para Business Server 2015.'
ms.openlocfilehash: 7c5abf07c5b30e4e015936fcf0987e989f1d8117
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>Realizar copia intermedia de certificados AV y OAuth en Skype Empresarial Server 2015 usando -Roll en Set-CsCertificate
 
**Resumen:** Fase AV y OAuth certificados para Skype para Business Server 2015.
  
Audio y vídeo (A / V) communications es un componente clave de Skype para Business Server 2015. Características como la conferencia de uso compartido y audio y vídeo de la aplicación se basan en los certificados asignados a los / servicio perimetral A/v, específicamente el A / servicio de autenticación de V.
  
> [!IMPORTANT]
> Esta nueva característica está diseñada para trabajar en lugar de A / servicio perimetral A/v y el certificado OAuthTokenIssuer. Otros tipos de certificados se pueden aprovisionar junto con el / servicio perimetral A/v y OAuth tipo de certificado, pero no se beneficiarán del comportamiento de coexistencia que el / será el certificado del servicio perimetral A/v.
  
El Skype para cmdlets de PowerShell de Shell de administración de servidor empresarial que se usan para administrar Skype para Business Server 2015 certificados hace referencia al servicio perimetral A/v como el tipo de certificado AudioVideoAuthentication y el certificado OAuthServer como typeOAuthTokenIssuer. Para el resto de este tema y para identificar de forma exclusiva los certificados, se utilizará el nombre para el mismo tipo de identificador, AudioVideoAuthentication andOAuthTokenIssuer.
  
El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan a partir de atributos del certificado y, cuando el certificado expira, se produce la pérdida de conexión y es necesario volver a unirse con un nuevo token generado por el nuevo certificado. Una nueva característica de Skype para Business Server 2015 va a solucionar este problema - la posibilidad de organizar un nuevo certificado antes de la antigua uno a expirar y permitir que ambos certificados continuar funcionando durante un período de tiempo. Esta característica usa funcionalidad actualizada en el Skype Set-CsCertificate para cmdlet del Shell de administración de servidor empresarial. El nuevo parámetro-Roll, con el parámetro existente - EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. A partir de la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:
  
> [!TIP]
> Usa el Skype para cmdlets de Shell de administración de servidor empresarial para la administración de certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. Usar al Asistente para certificados en el Skype para el Asistente para la implementación de servidor de Business le ayuda a crear certificados, pero normalmente es del tipo **predeterminado** qué parejas todos los certificados se usa para el servidor perimetral en un solo certificado. La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado. Puede aprovisionar y crear un acopia intermedia de un certificado del tipo predeterminado, pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará de ello. Un usuario utilizado (por ejemplo) en una conversación de mensajería cuando expire el certificado instantánea tendrá que cerrar la sesión y volver a iniciarla para realizar el uso del nuevo certificado asociado con el servicio de servidor perimetral de acceso. Se producirá un comportamiento similar para un usuario que participa en una conferencia Web con el servicio de servidor perimetral de conferencia Web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. Puede crear y administrar el certificado en un solo lugar y se almacena el certificado en el almacén de Administración Central para todos los demás servidores.
  
Se necesitan detalles adicionales para comprender por completo las opciones y los requisitos al usar el cmdlet Set-CsCertificate y al usarlo para realizar una copia intermedia de los certificados antes de la expiración del certificado actual. -Roll parámetro es importante, pero básicamente único propósito. Si define como un parámetro, está indicando a Set-CsCertificate que va a proporcionar información sobre el certificado que se verán afectado definido por - tipo (por ejemplo AudioVideoAuthentication y OAuthTokenIssuer), cuando se convertirán en el certificado eficaces definido por - EffectiveDate.
  
 **-Roll**:-Roll parámetro es necesario y tiene dependencias que se deben proporcionar junto con ella. Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:
  
 **-EffectiveDate**: el parámetro - EffectiveDate define cuando el nuevo certificado se convertirá en co-active con el certificado actual. -EffectiveDate puede estar cerca de la fecha de caducidad del certificado actual, o puede ser un período de tiempo más largo. Un recomendado mínimo - EffectiveDate para el certificado AudioVideoAuthentication serían 8 horas, que es la duración del token predeterminado para el servidor perimetral AV. tokens de servicio emitido mediante el certificado AudioVideoAuthentication.
  
Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.
  
 **-Thumbprint**: la huella digital es un atributo del certificado que es único para dicho certificado. La - huella digital del parámetro se usa para identificar el certificado que se verán afectado por las acciones del cmdlet Set-CsCertificate.
  
 **-Tipo**:-tipo de parámetro puede aceptar un tipo de uso único certificado o una lista separada por comas de tipos de uso de certificados. Los tipos de certificados son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, el tipo AudioVideoAuthentication es para su uso por el / servicio perimetral A/v y el servicio de autenticación de AV. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el mayor plazo efectivo mínimo para los certificados. Por ejemplo, tiene que organizar certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. Su - EffectiveDate mínimo debe ser mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea organizar el certificado AudioVideoAuthentication con un plazo de 24 horas, organícelo por separado con una EffectiveDate que se adapte más a sus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de servicio perimetral A/v con - Roll y - EffectiveDate parámetros

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicite una renovación o un nuevo certificado AudioVideoAuthentication con clave privada exportable para el certificado existente en el / servicio perimetral A/v.
    
3. Importe el nuevo certificado AudioVideoAuthentication para el servidor perimetral y todos los otros servidor perimetral en el grupo de servidores (si tiene un grupo de servidores implementado).
    
4. Configurar el certificado importado con el cmdlet Set-CsCertificate y usar parámetro - Roll con el parámetro - EffectiveDate. La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas). Esto nos da una hora en que el certificado se debe establecer en activo y es - EffectiveDate \<cadena\>: "22/7/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para un grupo de servidores perimetrales, debe tener todos los certificados AudioVideoAuthentication implementado y aprovisionados por la fecha y hora definidos por el parámetro - EffectiveDate del primer certificado implementado para evitar una posible / interrupción de V communications debido a la versión más antigua el certificado a expirar antes de que se han renovado todos los tokens de cliente y consumidor con el nuevo certificado. 
  
    El Set-CsCertificate de comando con el - parámetro Roll y - hora efectiva:
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
  ```

    Un comando Set-CsCertificate de ejemplo:
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
  ```

    > [!IMPORTANT]
    > El EffectiveDate debe tener el formato para que coincida con la región de su servidor y la configuración de idioma. En el ejemplo se usa la configuración de idioma y región inglés con nosotros 
  
Para comprender mejor el proceso que Set-CsCertificate, - Roll y - EffectiveDate se usa para organizar un nuevo certificado para emitir tokens de AudioVideoAuthentication nuevo sin dejar de usar un certificado existente para validar AudioVideoAuthentication que están en uso los consumidores, una escala de tiempo visual es un medio eficaz de descripción del proceso. En el siguiente ejemplo, el administrador determina que el certificado del servicio perimetral A/v es a punto de caducar a las 2:00:00 P.M. en 22/07/2015. Solicita y recibe un certificado nuevo y lo importa a cada servidor perimetral de su grupo de servidores. A las 2 A.M. en 22/07/2015, inicia la ejecución de Get-CsCertificate con - Roll, - huella digital igual a la cadena de la huella digital del certificado nuevo y - hora efectiva establecen en 22/07/2015 6:00:00 AM. Este comando ejecuta en cada servidor perimetral.
  
![Usar los parámetros Roll y EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Llamada**|**Fase**|
|:-----|:-----|
|1  <br/> |Inicio: 7/22/2015 12:00:00  <br/> El certificado AudioVideoAuthentication actual expirará a las 14:00:00 del día 22/7/2015. Esto está determinado por la marca de tiempo de expiración del certificado. Se debe planear la sustitución de certificado para que se produzca una superposición de 8 horas (vigencia de token predeterminada) antes de que el certificado actual alcance la hora de expiración. En este ejemplo, se usa la hora de inicio 2:00:00 para que el administrador tenga tiempo suficiente para colocar y suministrar los nuevos certificados antes de las 6:00:00, que es la hora efectiva.  <br/> |
|2  <br/> |7/22/2015 2:00:00 - 7/22/2015 5:59:59  <br/> Configurar certificados en los servidores perimetrales con tiempo eficaz de 6:00:00 AM (4 horas plazo es para este ejemplo, pero puede ser más larga) utilizando Set-CsCertificate-tipo \<tipo de uso del certificado\> -huella digital \<huella digital del certificado nuevo\> - Roll - EffectiveDate \<cadena de fecha y hora de la hora efectiva de nuevo certificado\>  <br/> |
|3  <br/> |7/22/2015 6:00 - 7/22/2015 14:00  <br/> Para validar tokens, primero se prueba el nuevo certificado y, si no valida el token, se prueba el certificado antiguo. Este proceso se usa para todos los tokens durante el período de 8 horas de superposición (vigencia predeterminada del token).  <br/> |
|4  <br/> |Final: 7/22/2015 14:00:01  <br/> El certificado antiguo ha expirado y se ha pasado a usar el nuevo certificado. Certificado antiguo puede quitarse de manera segura con Remove-CsCertificate-tipo \<tipo de uso del certificado\> -anterior  <br/> |
   
Cuando se alcanza la hora efectiva (22/07/2015 6:00:00), todos los nuevos tokens se emiten por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el certificado nuevo y recurrir al antiguo continuará hasta la hora de expiración del certificado antiguo. Una vez que el certificado antiguo haya expirado (22/07/2015 14:00:00), los tokens solo los validará el nuevo certificado. El certificado antiguo puede quitarse de manera segura con el cmdlet Remove-CsCertificate con el - parámetro anterior.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un OAuthTokenIssuer con - Roll y - EffectiveDate parámetros de certificados

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicite una renovación o un nuevo certificado OAuthTokenIssuer con clave privada exportable para el certificado existente en el servidor Front-End.
    
3. Importe el nuevo certificado OAuthTokenIssuer a un servidor Front-End en el grupo de servidores (si tiene un grupo de servidores implementado). El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que actualizar y renovar en cualquier servidor de su implementación. El servidor Front-End se usa como ejemplo.
    
4. Configurar el certificado importado con el cmdlet Set-CsCertificate y usar parámetro - Roll con el parámetro - EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas. 
    
    El Set-CsCertificate de comando con el - parámetro Roll y - hora efectiva:
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
  ```

Un comando Set-CsCertificate de ejemplo:
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> El EffectiveDate debe tener el formato para que coincida con la región de su servidor y la configuración de idioma. En el ejemplo se usa la configuración de idioma y región inglés con nosotros 
  
Cuando se alcanza la hora efectiva (21/07/2015 01:00:00), el nuevo certificado emite todos los tokens nuevos. Al validar los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el certificado nuevo y recurrir al antiguo continuará hasta la hora de expiración del certificado antiguo. Una vez que el certificado antiguo haya expirado (22/07/2015 14:00:00), los tokens solo los validará el nuevo certificado. El certificado antiguo puede quitarse de manera segura con el cmdlet Remove-CsCertificate con el - parámetro anterior.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vea también

#### 

[Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server 2015](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

