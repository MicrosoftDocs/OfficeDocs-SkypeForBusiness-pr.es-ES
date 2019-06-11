---
title: 'Lync Server 2013: Configurar certificados para la interfaz perimetral interna'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53ba11db5d2c9fc727b7720a1a10d5da547075c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configurar certificados para la interfaz perimetral interna en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Cuando ejecute el Asistente para certificados, asegúrese de haber iniciado sesión con una cuenta que sea miembro de un grupo al que se le hayan asignado los permisos adecuados para el tipo de plantilla de certificado que va a usar. De forma predeterminada, una solicitud de certificado de Lync Server 2013 usará la plantilla de certificado de servidor Web. Si usa una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado con esta plantilla, compruebe que el grupo tiene asignados los permisos de inscripción necesarios para usar esa plantilla.



</div>

Se necesita un único certificado en la interfaz interna de cada servidor perimetral. Los certificados de la interfaz interna pueden ser emitidos por una entidad de certificación (CA) interna o una CA pública. Si su organización tiene una CA interna implementada, puede ahorrar en el gasto de usar certificados públicos mediante la entidad de certificación interna para emitir el certificado de la interfaz interna. Puede usar una CA interna de Windows Server 2008 o una CA de Windows Server 2008 R2 para crear estos certificados.

Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para configurar certificados en la interfaz de borde interno en un sitio, siga los procedimientos de esta sección para hacer lo siguiente:

1.  Descarga la cadena de certificación de la entidad emisora para la interfaz interna de cada servidor perimetral.

2.  Importe la cadena de certificación de la entidad de certificación de la interfaz interna en cada servidor perimetral.

3.  Cree la solicitud de certificado para la interfaz interna, en un servidor perimetral, denominado el primer servidor perimetral.

4.  Importe el certificado de la interfaz interna en el primer servidor perimetral.

5.  Importe el certificado en los otros servidores perimetrales de este sitio (o implementado detrás de este equilibrador de carga).

6.  Asigne el certificado de la interfaz interna de cada servidor perimetral.

Si tiene más de un sitio con servidores perimetrales (es decir, una topología perimetral de varios sitios) o conjuntos independientes de servidores perimetrales implementados con distintos equilibradores de carga, debe seguir estos pasos para cada sitio que tenga servidores perimetrales y para cada conjunto de servidores perimetrales. implementado detrás de un equilibrador de carga diferente.

<div>


> [!NOTE]  
> Los pasos de esta sección se basan en el uso de una CA de&nbsp;windows Server 2008, windows&nbsp;Server&nbsp;2008 R2 CA, Windows server 2012 CA o Windows Server 2012 R2 CA para crear un certificado para cada servidor perimetral. Para obtener instrucciones paso a paso para cualquier otra CA, consulte la documentación de esa CA. De forma predeterminada, todos los usuarios autenticados tienen los derechos de usuario adecuados para solicitar certificados.<BR>Los procedimientos de esta sección se basan en la creación de solicitudes de certificado en el servidor perimetral como parte del proceso de implementación del servidor perimetral. Es posible crear solicitudes de certificados con el servidor front-end. Puede hacerlo para completar la solicitud de certificado al principio del proceso de planeación e implementación, antes de iniciar la implementación de los servidores perimetrales. Para ello, debe asegurarse de que el certificado solicitado se haya definido con una clave privada exportable.<BR>Los procedimientos de esta sección describen el uso de un archivo. cer y un archivo. p7b para el certificado. Si usa un tipo de archivo diferente, modifique estos procedimientos según corresponda.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Para descargar la cadena de certificación de CA para la interfaz interna mediante el sitio web certsrv

1.  Inicie sesión en un servidor de Lync Server 2013 de la red interna (es decir, no en el servidor perimetral) como miembro del grupo **administradores** .

2.  Ejecute el comando siguiente en un símbolo del sistema haciendo clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba lo siguiente:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Por ejemplo:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Si está usando Windows Server 2008 o Windows Server 2008 R2 Enterprise CA, debe usar https, no http.

    
    </div>

3.  En la página web certsrv de la CA que emite el certificado, en **Seleccione una tarea**, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.

4.  En **descargar un certificado de CA, una cadena de certificados o una CRL**, haga clic en **Descargar cadena de certificados**de la entidad emisora.

5.  En el cuadro de diálogo **descarga de archivos** , haga clic en **Guardar**.

6.  Guarde el archivo. p7b en la unidad de disco duro del servidor y, a continuación, cópielo en una carpeta de cada servidor perimetral.
    
    <div>
    

    > [!NOTE]  
    > El archivo. p7b contiene todos los certificados que se encuentran en la ruta de certificación. Para ver la ruta de certificación, abra el certificado de servidor y haga clic en la ruta de certificación.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Para exportar la cadena de certificación de la CA para la interfaz interna con MMC

1.  Puede exportar el certificado raíz de la entidad emisora desde cualquier equipo unido a un dominio mediante la consola de administración de Microsoft (MMC). Haga clic en **Inicio**, haga clic en **Ejecutar**y escriba **MMC**.

2.  En la consola MMC, haga clic en **archivo**y en **Agregar o quitar**.

3.  En la lista de cuadros de diálogo **Agregar o quitar complementos** , seleccione **certificados**y, a continuación, haga clic en **Agregar**. Cuando se le solicite, seleccione **cuenta de equipo**. En el diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga clic en **Finalizar**. Haga clic en **Aceptar**.

4.  Expanda **certificados (equipo local)**. Expanda **entidades de certificación raíz de confianza**, seleccione **certificados**.

5.  Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón secundario en el certificado, seleccione **todas las tareas**y **exportar**. Se abrirá el **Asistente para exportación de certificados** .

6.  En el **Asistente para exportación de certificados**, haga clic en **siguiente**.

7.  En el cuadro de diálogo **exportar formato de archivo** , seleccione un formato para exportar. Recomendamos el **estándar de sintaxis de mensajes criptográficos \#: certificados PKCS 7 (. P7B)**. Si selecciona la **Sintaxis de mensajes criptográficos estándar: certificados \#PKCS 7 (. P7B)**, seleccione la casilla **incluir todos los certificados en la ruta de certificación si es posible** para exportar la cadena de certificados, incluido el certificado de CA raíz y los certificados de CA intermedias. Haga clic en **Siguiente**.

8.  En el cuadro de diálogo **archivo para exportar** , en la entrada nombre de archivo, escriba una ruta de acceso y un nombre de archivo (la extensión predeterminada es. p7b) para el certificado exportado. De manera opcional, haga clic en **examinar**, busque un directorio en el que ubicar el certificado exportado y proporcione un nombre para el certificado exportado. Haga clic en **Guardar **. Haga clic en **Siguiente**.

9.  Revise el Resumen de acciones y haga clic en **Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Para importar la cadena de certificación de CA de la interfaz interna

1.  En cada servidor perimetral, abra Microsoft Management Console (MMC) haciendo clic en **Inicio**, haga clic en **Ejecutar**, escriba **MMC** en el cuadro **abrir** y, a continuación, haga clic en **Aceptar**.

2.  En el menú **archivo** , haga clic en **Agregar o quitar complemento**y, a continuación, haga clic en **Agregar**.

3.  En el cuadro **Agregar complementos independientes** , haga clic en **certificados**y, a continuación, haga clic en **Agregar**.

4.  En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.

5.  En el cuadro de diálogo **seleccionar equipo** , asegúrese de que la casilla **equipo local: (el equipo en el que se está ejecutando esta consola)** está activada y, a continuación, haga clic en **Finalizar**.

6.  Haga clic en **cerrar**y, a continuación, en **Aceptar**.

7.  En el árbol de consola, expanda **certificados (equipo local)**, haga clic con el botón secundario en **entidades emisoras raíz de confianza**, seleccione **todas las tareas**y haga clic en **importar**.

8.  En el asistente, en **archivo para importar**, especifique el nombre de archivo del certificado (es decir, el nombre que especificó al descargar la cadena de certificación de la entidad emisora para la interfaz interna en el procedimiento anterior).

9.  Repita este procedimiento en cada servidor perimetral.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Para crear la solicitud de certificado para la interfaz interna

1.  En uno de los servidores perimetrales, inicie el Asistente para la implementación y, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.
    
    <div>
    

    > [!NOTE]  
    > Si tiene varios servidores perimetrales en una ubicación de un grupo, puede ejecutar el Asistente para certificados en cualquiera de los servidores perimetrales.<BR>Después de ejecutar el paso 3 por primera vez, el botón cambiará a <STRONG>ejecutarse</STRONG>y una marca de verificación verde que indica que la tarea se completó correctamente no se mostrará hasta que se hayan solicitado, instalado y asignado todos los certificados necesarios.

    
    </div>

2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **solicitud de certificado** , haga clic en **siguiente**.

4.  En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.

5.  En la página **archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo en el que se va a guardar la solicitud (por ejemplo, **c:\\CERT\_Internal\_Edge. cer**).

6.  En la página **especificar plantilla de certificado alternativa** , para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla **Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada** .

7.  En la página **nombre y configuración de seguridad** , haga lo siguiente:
    
      - En **nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, contorno interno).
    
      - En **longitud bit**, especifique la longitud en bits (normalmente, el valor predeterminado de **2048**).
        
        <div>
        

        > [!NOTE]  
        > Las longitudes de bits más altas ofrecen más seguridad pero tienen un impacto negativo en la velocidad.

        
        </div>
    
      - Si es necesario exportar el certificado, active la casilla **marcar clave privada de certificado como** exportable.

8.  En la página información de la **organización** , escriba el nombre de la organización y la unidad organizativa (OU) (por ejemplo, una división o un departamento).

9.  En la página **información geográfica** , especifique la información de ubicación.

10. En la página **nombre de sujeto/nombres alternativos de asunto** , se muestra la información que el asistente rellenará automáticamente.

11. En la página **configurar otros nombres alternativos de asunto** , especifique los nombres alternativos adicionales que sean obligatorios.

12. En la página Resumen de la **solicitud** , revise la información del certificado que se va a usar para generar la solicitud.

13. Una vez completados los comandos, haga lo siguiente:
    
      - Para ver el registro de la solicitud de certificado, haga clic en **Ver registro**.
    
      - Para completar la solicitud de certificado, haga clic en **siguiente**.

14. En la página **archivo de solicitud de certificado** , haga lo siguiente:
    
      - Para ver el archivo de solicitud de firma de certificado generado (CSR), haga clic en **Ver**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.

15. Envíe este archivo a la entidad emisora (por correo electrónico u otro método admitido por su organización para la entidad emisora de certificados de empresa) y, cuando reciba el archivo de respuesta, copie el nuevo certificado en este equipo para que esté disponible para la importación.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Para importar el certificado de la interfaz interna

1.  Inicie sesión en el servidor perimetral en el que creó la solicitud de certificado como miembro del grupo de administradores local.

2.  En el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    Después de ejecutar el paso 3 por primera vez, el botón cambia **** a ejecutarse, pero no se muestra una marca de verificación verde (que indica que la tarea se ha completado correctamente) hasta que se hayan solicitado, instalado y asignado todos los certificados necesarios.

3.  En la página **tareas de certificados disponibles** , haga clic en **importar un certificado desde un. Archivo P7b,. pfx o. cer**.

4.  En la página **importar certificado** , escriba la ruta de acceso completa y el nombre de archivo del certificado que solicitó y recibió para la interfaz interna de este servidor perimetral (o bien, haga clic en **examinar** para buscar y seleccionar el archivo).

5.  Si va a importar certificados de otros miembros del grupo, un certificado que contenga una clave privada, seleccione la casilla el **archivo de certificado contiene la clave privada del certificado** y especifique la contraseña.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar el certificado con la clave privada para servidores perimetrales en un grupo de servidores

1.  Inicie sesión como miembro del grupo administradores en el mismo servidor perimetral en el que importó el certificado.

2.  Haga clic en **Inicio**, haga clic en **Ejecutar**y escriba **MMC**.

3.  Desde la consola MMC, haga clic en **archivo**y en **Agregar o quitar complemento**.

4.  En la página Agregar o quitar complementos, haga clic en **certificados**y, después, en **Agregar**.

5.  En el cuadro de diálogo del complemento certificados, seleccione **cuenta de equipo**. Haga clic en **Siguiente**. En seleccionar equipo, seleccione **equipo local: (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** para completar la configuración de la consola MMC.

6.  Haga doble clic en **Certificados (equipo local)** para expandir los almacenes de certificados. Haga doble clic en **personal**y, a continuación, haga doble clic en **certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si no hay certificados en el almacén personal de certificados para el equipo local, no hay ninguna clave privada asociada al certificado que se importó. Revise los pasos de la solicitud e importar. Si el problema persiste, póngase en contacto con el administrador o el proveedor de su entidad de certificación.

    
    </div>

7.  En el almacén personal de certificados del equipo local, haga clic con el botón secundario en el certificado que va a exportar. Haga clic en **todas las tareas**, en **exportar**.

8.  En el Asistente para exportación de certificados, haga clic en **siguiente**. Seleccione **sí, exportar la clave privada**. Haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si la selección <STRONG>sí, exportar la clave privada</STRONG> no está disponible, la clave privada asociada a este certificado no se marcó para exportar. Tendrá que volver a solicitar el certificado, lo que garantiza que el certificado estará marcado para permitir la exportación de la clave privada antes de poder continuar con la exportación. Póngase en contacto con el administrador o proveedor de su entidad de certificación.

    
    </div>

9.  En el cuadro de diálogo Exportar formatos de archivo, seleccione **intercambio de\#información personal – PKCS 12 (. PFX)** y, a continuación, seleccione lo siguiente:
    
      - Incluir todos los certificados en la ruta de certificación si es posible
    
      - Exportar todas las propiedades extendidas
        
        <div>
        

        > [!WARNING]  
        > Al exportar el certificado desde un servidor perimetral, no seleccione <STRONG>eliminar la clave privada si la exportación es correcta</STRONG>. Si selecciona esta opción, necesitará importar el certificado y la clave privada a este servidor perimetral.

        
        </div>
    
    Haga clic en **Siguiente** para continuar.

10. Si desea asignar una contraseña para proteger la clave privada, escriba una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmarla. Haga clic en **Siguiente**.

11. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo .pfx. La ruta de acceso debe ser accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte por medio de medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente**.

12. Revise el resumen en el cuadro de diálogo completando el Asistente para exportación de certificados. Haga clic en **Finalizar**.

13. Haga clic en **Aceptar** en el cuadro de diálogo de exportación correcta.

14. Importe el archivo de certificado exportado a los otros servidores perimetrales siguiendo los pasos descritos en los procedimientos de [configuración de certificados para la interfaz de borde externo de Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Para asignar el certificado interno en los servidores perimetrales

1.  En cada servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

2.  En la página **tareas de certificados disponibles** , haga clic en **asignar un certificado existente**.

3.  En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.

4.  En la página **almacén de certificados** , seleccione el certificado importado para el contorno interno (desde el procedimiento anterior).

5.  En la página **Resumen de asignación de certificado** , revise la configuración y, a continuación, haga clic en **siguiente** para asignar los certificados.

6.  En la página de finalización del asistente, haga clic en **Finalizar**.

7.  Después de usar este procedimiento para asignar el certificado de contorno interno, abra el complemento certificado en cada servidor, expanda **certificados (equipo local)**, expanda **personal**, haga clic en **certificados**y, después, compruebe en el panel de detalles el certificado de contorno interno aparece en la lista.

8.  Si su implementación incluye varios servidores perimetrales, repita este procedimiento para cada servidor perimetral.

</div>

</div>

<span> </span>

</div>

</div>

</div>

