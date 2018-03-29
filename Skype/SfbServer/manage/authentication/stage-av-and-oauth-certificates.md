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
description: 'Resumen: Fase AV y OAuth certificados para Skype para Business Server 2015.'
ms.openlocfilehash: 4117707e7a86833ebb235100c26e27d16e1df9db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>Realizar copia intermedia de certificados AV y OAuth en Skype Empresarial Server 2015 usando -Roll en Set-CsCertificate
 
**Resumen:** Etapa AV y OAuth certificados para Skype para Business Server 2015.
  
Audio y vídeo (A / V) communications es un componente clave de Skype para Business Server 2015. Características como aplicación para compartir y videoconferencias dependen de los certificados asignados a la A / servicio de borde V, específicamente A / servicio de autenticación de V.
  
> [!IMPORTANT]
> Esta nueva característica está diseñada para funcionar en lugar de A / servicio V perimetral y el certificado OAuthTokenIssuer. Otros tipos de certificados se pueden aprovisionar junto con el / servicio V perimetral y OAuth tipo de certificado, pero no se beneficiarán del comportamiento de coexistencia que el certificado del servicio V borde será.
  
El Skype para cmdlets de PowerShell de Shell de administración de Business Server utilizados para administrar Skype para certificados de servidor de negocios 2015 se refiere a la A o borde V de servicio como el tipo de certificado de AudioVideoAuthentication y el certificado de OAuthServer como typeOAuthTokenIssuer. Para el resto de este tema y para identificar de forma exclusiva los certificados, se utilizará el nombre para el mismo tipo de identificador, AudioVideoAuthentication andOAuthTokenIssuer.
  
El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan a partir de atributos del certificado y, cuando el certificado expira, se produce la pérdida de conexión y es necesario volver a unirse con un nuevo token generado por el nuevo certificado. Una nueva característica de Skype para Business Server 2015 aliviar este problema: la capacidad de ensayar un nuevo certificado con antelación unas caducan y permitir que ambos certificados siga funcionando durante un período de tiempo. Esta característica utiliza la funcionalidad actualizada en el conjunto CsCertificate de Skype para el cmdlet del Shell de administración de servidor empresarial. El nuevo parámetro-Roll, con el parámetro existente - EffectiveDate, colocará el nuevo certificado de AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. A partir de la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:
  
> [!TIP]
> Utiliza el Skype para los cmdlets del Shell de administración de servidor de negocios para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. Utilizando al Asistente para certificados en el Skype para el Asistente para implementación de Business Server le ayuda a crear certificados, pero normalmente es del tipo **predeterminado** qué parejas todos los certificados se utiliza para el servidor perimetral en un solo certificado. La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado. Puede aprovisionar y crear un acopia intermedia de un certificado del tipo predeterminado, pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará de ello. Un usuario implicado (por ejemplo) en una conversación de mensajería cuando caduca el certificado instantánea deberá cerrar la sesión y volver a iniciarla para hacer uso del nuevo certificado asociado con el servicio de servidor perimetral de acceso. Se producirá un comportamiento similar para los usuarios implicados en una conferencia Web con el servicio perimetral de conferencia Web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. Crear y administrar los certificados en un solo lugar y se almacena el certificado en el almacén de Administración Central para todos los demás servidores.
  
Se necesitan detalles adicionales para comprender por completo las opciones y los requisitos al usar el cmdlet Set-CsCertificate y al usarlo para realizar una copia intermedia de los certificados antes de la expiración del certificado actual. -Roll parámetro es importante, pero básicamente único propósito. Si se define como un parámetro, está indicando a conjunto CsCertificate que va a proporcionar información acerca del certificado que se verán afectado definido por - tipo (por ejemplo AudioVideoAuthentication y OAuthTokenIssuer), cuando se convertirá en el certificado efectivo definido por - EffectiveDate.
  
 **-Roll**:-Roll parámetro es necesario y tiene dependencias que deben proporcionarse junto con ella. Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:
  
 **-EffectiveDate**: el parámetro - EffectiveDate define cuándo el nuevo certificado se convertirá en CO-activo con el certificado actual. EffectiveDate - puede estar cerca de la fecha de caducidad del certificado actual, o puede ser un período de tiempo más largo. Recomendado un mínimo EffectiveDate - para el certificado de AudioVideoAuthentication sería de 8 horas, cuál es la duración del token predeterminado de tokens de servicio perimetral AV emitido mediante el certificado AudioVideoAuthentication.
  
Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.
  
 **-Thumbprint**: la huella digital es un atributo del certificado que es único para dicho certificado. -Huella digital del parámetro se utiliza para identificar el certificado que se verán afectado por las acciones del cmdlet Set-CsCertificate.
  
 **-Tipo**:-tipo de parámetro puede aceptar un tipo de uso de certificado único o una lista separada por comas de los tipos de uso de certificados. Los tipos de certificados son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, el tipo AudioVideoAuthentication es para su uso por el A / servicio V perimetral y el servicio de autenticación audiovisual. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el mayor plazo efectivo mínimo para los certificados. Por ejemplo, tiene que organizar certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. Su EffectiveDate - mínimo debe ser el mayor de los dos certificados, en este caso, el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea organizar el certificado AudioVideoAuthentication con un plazo de 24 horas, organícelo por separado con una EffectiveDate que se adapte más a sus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar una A / servicio perimetral V certificado con un - Roll y EffectiveDate - parámetros

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicitar una renovación o un nuevo certificado de AudioVideoAuthentication con exportable clave privada para el certificado existente en el A / servicio V perimetral.
    
3. Importar el nuevo certificado de AudioVideoAuthentication para el servidor perimetral y todos los otros servidor perimetral en su grupo (si tiene un grupo implementado).
    
4. Configurar el certificado importado con el cmdlet Set-CsCertificate y utilizar parámetro - Roll con el parámetro - EffectiveDate. La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas). Esto nos da una hora que el certificado se debe establecer como activo y es EffectiveDate - \<cadena\>: "22/7/2015 6:00:00 A.M.". 
    
    > [!IMPORTANT]
    > Para un grupo de borde, debe tener todos los certificados de AudioVideoAuthentication implementado y configurado por la fecha y hora definidos por el parámetro - EffectiveDate del primer certificado implementado para evitar una posible / interrupción de V communications debido a la versión más antigua certificado caduque antes de que se han renovado todos los tokens de cliente y consumidor con el nuevo certificado. 
  
    El conjunto de CsCertificate comando con el rollo y EffectiveTime - parámetro:
    
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
    > El EffectiveDate debe estar formateado para que coincida con la configuración de idioma y región de su servidor. En el ejemplo se utiliza la configuración de idioma y región de inglés nos 
  
Para comprender mejor el proceso de ese conjunto CsCertificate, - Roll y uso de - EffectiveDate para ensayar un nuevo certificado para emitir nuevos testigos de AudioVideoAuthentication y seguir utilizando un certificado existente para validar AudioVideoAuthentication que están en uso los consumidores, una escala de tiempo visual constituye un medio eficaz de entender el proceso. En el ejemplo siguiente, el administrador determina que el certificado del servicio de borde V es expirará a las 2:00:00 P.M. el 22/07/2015. Solicita y recibe un certificado nuevo e importa en cada servidor perimetral en su grupo. A las 2 A.M. el 22/07/2015, empieza ejecutando Get-CsCertificate con - Roll, - huella digital igual a la cadena de la huella digital del certificado nuevo y - EffectiveTime establecen en 22/07/2015 6:00:00 AM. Este cliente ejecuta este comando en cada servidor perimetral.
  
![Usar los parámetros Roll y EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Llamada**|**Fase**|
|:-----|:-----|
|1  <br/> |Inicio: 7/22/2015 12:00:00  <br/> El certificado AudioVideoAuthentication actual expirará a las 14:00:00 del día 22/7/2015. Esto está determinado por la marca de tiempo de expiración del certificado. Se debe planear la sustitución de certificado para que se produzca una superposición de 8 horas (vigencia de token predeterminada) antes de que el certificado actual alcance la hora de expiración. En este ejemplo, se usa la hora de inicio 2:00:00 para que el administrador tenga tiempo suficiente para colocar y suministrar los nuevos certificados antes de las 6:00:00, que es la hora efectiva.  <br/> |
|2  <br/> |7/22/2015 2:00:00 - 7/22/2015 5:59:59  <br/> Configurar certificados en servidores perimetrales con tiempo efectivo de 6:00:00 A.M. (4 horas tiempo de adelanto es para este ejemplo, pero puede ser más larga) utilizando el conjunto CsCertificate-tipo \<tipo de uso de certificados\> -huella digital \<huella digital del certificado nuevo\> - Roll - EffectiveDate \<cadena de fecha y hora de tiempo efectivo de certificado nuevo\>  <br/> |
|3  <br/> |7/22/2015 6:00 - 7/22/2015 14:00  <br/> Para validar tokens, primero se prueba el nuevo certificado y, si no valida el token, se prueba el certificado antiguo. Este proceso se usa para todos los tokens durante el período de 8 horas de superposición (vigencia predeterminada del token).  <br/> |
|4  <br/> |Final: 7/22/2015 14:00:01  <br/> El certificado antiguo ha expirado y se ha pasado a usar el nuevo certificado. Certificado antiguo puede quitarse con seguridad con quitar CsCertificate-tipo \<tipo de uso de certificados\> -anterior  <br/> |
   
Cuando se alcanza la hora efectiva (22/07/2015 6:00:00), todos los nuevos tokens se emiten por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el certificado nuevo y recurrir al antiguo continuará hasta la hora de expiración del certificado antiguo. Una vez que el certificado antiguo haya expirado (22/07/2015 14:00:00), los tokens solo los validará el nuevo certificado. El certificado antiguo se puede quitar mediante el cmdlet Remove-CsCertificate con el anterior parámetro-.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para actualizar o renovar un OAuthTokenIssuer con un - Roll y EffectiveDate - parámetros de certificados

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Solicitar una renovación o OAuthTokenIssuer un nuevo certificado con la clave privada puede exportar el certificado existente en el servidor Front-End.
    
3. Importar el nuevo certificado de OAuthTokenIssuer a un servidor Front-End en su grupo (si tiene un grupo implementado). El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que actualizar y renovar en cualquier servidor de su implementación. El servidor Front-End se utiliza como ejemplo.
    
4. Configurar el certificado importado con el cmdlet Set-CsCertificate y utilizar parámetro - Roll con el parámetro - EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas. 
    
    El conjunto de CsCertificate comando con el rollo y EffectiveTime - parámetro:
    
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
> El EffectiveDate debe estar formateado para que coincida con la configuración de idioma y región de su servidor. En el ejemplo se utiliza la configuración de idioma y región de inglés nos 
  
Cuando se alcanza la hora efectiva (21/07/2015 01:00:00), el nuevo certificado emite todos los tokens nuevos. Al validar los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el certificado nuevo y recurrir al antiguo continuará hasta la hora de expiración del certificado antiguo. Una vez que el certificado antiguo haya expirado (22/07/2015 14:00:00), los tokens solo los validará el nuevo certificado. El certificado antiguo se puede quitar mediante el cmdlet Remove-CsCertificate con el anterior parámetro-.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vea también

#### 

[Administrar la autenticación de servidor a servidor (OAuth) y aplicaciones de los socios en Skype para Business Server 2015](server-to-server-and-partner-applications.md)
#### 

[Conjunto de CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Quitar CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

