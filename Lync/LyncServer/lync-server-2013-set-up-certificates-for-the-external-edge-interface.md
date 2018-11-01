---
title: 'Lync Server 2013: Configurar certificados para la interfaz perimetral externa'
TOCTitle: Configurar certificados para la interfaz perimetral externa
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48275406
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados para la interfaz perimetral externa en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

> [!IMPORTANT]  
> Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use. De manera predeterminada, una solicitud de certificado de Lync Server usará la plantilla de certificado Servidor web. Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.



Cada servidor perimetral requiere un certificado público en la interfaz entre la red perimetral e Internet. Asimismo, el nombre alternativo de sujeto del certificado debe contener los nombres externos de los nombres de dominio completos (FQDN) del servicio perimetral de acceso y del servicio perimetral de conferencia web.

Para obtener información detallada sobre este y otros requisitos de certificado, vea [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para obtener una lista de las autoridades de certificación pública (CA) que proporcionan certificados que cumplen requisitos específicos para certificados de comunicaciones unificadas y están asociadas con Microsoft para asegurar que funcionan con el Asistente para certificados de Lync Server 2013, consulte el artículo 929395 de Microsoft Knowledge Base, "Empresas colaboradoras de certificados de comunicaciones unificadas para Exchange Server 2007 y para Communications Server 2007" en <http://go.microsoft.com/fwlink/?linkid=202834>.

## Configurar los certificados en las interfaces externas

Para configurar un certificado en la interfaz perimetral externa de un sitio, use los procedimientos de esta sección para:

  - Crear la solicitud de certificado para la interfaz externa del servidor perimetral.

  - Enviar la solicitud a la entidad de certificación pública.

  - Importar el certificado en la interfaz externa de cada servidor perimetral.

  - Asignar el certificado a la interfaz externa de cada servidor perimetral.

  - Si su implementación tiene varios servidores perimetrales, exporte los certificados junto con su clave privada y cópielos a los demás servidores perimetrales. A continuación, en cada servidor perimetral, impórtelo y asígnelo tal como se ha descrito anteriormente. Repita este procedimiento con todos los servidores perimetrales.

Puede solicitar certificados públicos directamente a una autoridad de certificación pública (CA) (como, por ejemplo, desde el sitio web de una CA pública). Los procedimientos de esta sección usan el Asistente para certificados para la mayoría de tareas de certificados. Si decide solicitar directamente un certificado a una CA pública, entonces no tendrá que modificar cada procedimiento según sea apropiado para solicitar, transportar e importar el certificado, así como para importar la cadena de certificados.

Cuando solicite un certificado a una entidad de certificación externa, las credenciales proporcionadas deben tener derechos para solicitar un certificado a dicha entidad. Cada entidad de certificación tiene una directiva de seguridad que define qué credenciales (es decir, qué nombres de usuario y grupo específicos) se permiten para solicitar, emitir, administrar o leer certificados.

Si decide usar la Microsoft Management Console (MMC) de los certificados para importar la cadena de certificados y los certificados, deberá importarlos al almacén de certificados del equipo. Si los importa al almacén de certificados del usuario o del servicio, el certificado no se podrá asignar en el Asistente para certificados de Lync Server 2013.

## Para crear la solicitud de certificado para la interfaz externa del servidor perimetral

1.  En el Asistente para la implementación del servidor perimetral, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    

    > [!NOTE]
    > Si la organización desea admitir la conectividad de mensajería instantánea pública con AOL, no puede usar Asistente para la implementación de Lync Server para solicitar certificados. En su lugar, se deben realizar los pasos descritos en "Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para permitir la conectividad de mensajería instantánea pública con AOL" que encontrará más adelante en este tema.<BR>Si tiene varios servidores perimetrales en una ubicación de un grupo de servidores, puede ejecutar el Asistente para certificados de Lync Server 2013 en cualquiera de los servidores perimetrales.



2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.

4.  En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.

5.  En la página **Archivo de solicitud de certificados** , escriba la ruta de acceso completa y el nombre del archivo en el que se guardará la solicitud (por ejemplo, c:\\cert\_exernal\_edge.cer).

6.  En la página **Especificar plantilla de certificado alternativa** , para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada** .

7.  En la página **Nombre y configuración de seguridad**, siga este procedimiento:
    
      - En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado.
    
      - En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es **2048**).
    
      - Compruebe que la casilla **Marcar la clave privada del certificado como exportable** está activada.

8.  En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).

9.  En la página **Información geográfica** , escriba la información de ubicación.

10. En la página **Nombre de sujeto/nombres alternativos de sujeto** , la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos del firmante, especifíquelos en los dos pasos siguientes.

11. En la página **Configuración del dominio SIP en nombres alternativos de sujeto (SAN)** , active la casilla del dominio para agregar una entrada sip. *\<sipdomain\>* a la lista de nombres alternativos de sujeto.

12. En la página **Configurar nombres alternativos de sujeto adicionales**, especifique cualquier nombre alternativo del firmante adicional que necesite.

13. En la página **Resumen de la solicitud**, revise la información del certificado que va a usar para generar la solicitud.

14. Cuando finalice la ejecución de los comandos, haga lo siguiente:
    
      - Para visualizar el registro de la solicitud de certificación, haga clic en **Ver registro**.
    
      - Para completar la solicitud de certificación, haga clic en **Siguiente**.

15. En la página **Archivo de solicitud de certificados**, haga lo siguiente:
    
      - Para visualizar el archivo de solicitud de firma de certificado (CSR) que se ha generado, haga clic en **Ver**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.

16. Copie el archivo de resultados en una ubicación donde pueda enviarlo a la entidad de certificación pública.

## Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para que admita la conectividad de mensajería instantánea pública con AOL

1.  Cuando la plantilla necesaria esté disponible para la entidad de certificación, use el siguiente cmdlet Windows PowerShell del servidor perimetral para solicitar el certificado:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    El nombre predeterminado del certificado de la plantilla proporcionada por Lync Server 2013 es Web Server. Especifique solo el *\<nombre de plantilla\>* si necesita usar una plantilla distinta de la plantilla predeterminada.
    

    > [!NOTE]
    > Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del Asistente para certificados para solicitar el certificado que va a asignar al perimetral externo para el servicio perimetral de acceso. Esta es la razón por la que la plantilla Web Server de Lync Server 2013 que usa el Asistente para certificados para solicitar un certificado no permite la configuración EKU de cliente. Antes de usar Windows PowerShell para crear un certificado, el administrador de la entidad de certificación debe crear e implementar una nueva plantilla compatible con EKU de cliente.



## Para enviar una solicitud a una entidad de certificación pública

1.  Abra el archivo de resultados.

2.  Copie y pegue el contenido de la Solicitud de firma de certificado (CSR).

3.  Si se le solicita, especifique lo siguiente:
    
      - **Microsoft** como la plataforma de servidor.
    
      - **IIS** como la versión.
    
      - **Web Server** como el tipo de uso.
    
      - **PKCS7** como el formato de respuesta.

4.  Después de que la entidad de certificación pública compruebe toda la información, recibirá un mensaje de correo electrónico con el texto requerido para el certificado.

5.  Copie el texto del mensaje de correo electrónico y guarde el contenido en un archivo de texto (.txt) en su equipo local.

## Para importar el certificado para la interfaz externa del servidor perimetral

1.  Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que creó la solicitud de certificado.

2.  En el Asistente para la implementación, en la página **Implementar el servidor perimetral**, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

3.  En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.

4.  En la página **Importar certificado** , haga clic en **Examinar** para localizar y seleccionar el certificado que ha solicitado para la interfaz externa del servidor perimetral (también puede escribir la ruta completa y el nombre de archivo). Si el certificado contiene una clave privada, seleccione **El archivo del certificado contiene la clave privada del certificado** y escriba la contraseña de la clave privada. Haga clic en **Siguiente** .

5.  En la página **Importar resumen de certificado**, revise el resumen y, entonces, haga clic en **Siguiente**.

6.  En **Ejecutar comandos** , revise los resultados de la importación, haga clic en **Ver registro** si necesita más información y, entonces, haga clic en **Finalizar** para completar la importación del certificado.

7.  Si está configurando un grupo de servidores perimetral, exporte el certificado con su clave privada como se indica en el procedimiento "Para exportar el certificado con la clave privada para servidores perimetrales de un grupo" que encontrará más adelante en este tema. Copie el archivo del certificado exportado en los servidores perimetrales e impórtelo en el almacén del equipo de cada servidor perimetral.

## Para exportar el certificado con la clave privada para servidores perimetrales de un grupo

1.  Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que desea importar el certificado.

2.  Haga clic en **Inicio**, en **Ejecutar** y escriba **MMC**.

3.  En la consola Microsoft Management Console (MMC), haga clic en **Archivo** y, entonces, haga clic en **Agregar o quitar complemento**.

4.  En **Agregar o quitar complemento**, haga clic en **Certificados** y, entonces, en **Agregar** .

5.  En el cuadro de diálogo **Certificados** , seleccione **Cuenta de equipo** , haga clic en **Siguiente** , seleccione **Equipo local: (el equipo en el que se ejecuta esta consola)** en **Seleccionar equipo** , haga clic en **Finalizar** y, después, en **Aceptar** para finalizar la configuración de la consola MMC.

6.  Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados, haga doble clic en **Personal** y, a continuación, haga doble clic en **Certificados**.
    
    > [!IMPORTANT]  
    > Si no hay certificados en el almacén Certificados Personal para el equipo local, no habrá una clave privada asociada al certificado que se importó. Revise los pasos para la solicitud y la importación. Si el problema continúa, póngase en contacto con su administrador o proveedor de entidades de certificación.
    


7.  En el **almacén Certificados Personal del equipo local**, haga clic con el botón secundario en el certificado que va a exportar, haga clic en **Todas las tareas** y, a continuación, haga clic en **Exportar**.

8.  En el asistente para exportación de certificados, haga clic en **Siguiente** , seleccione **Exportar la clave privada** y, a continuación, haga clic en **Siguiente**.
    

    > [!NOTE]
    > Si la opción <STRONG>Exportar la clave privada</STRONG> no se encuentra disponible, se deberá a que no se marcó la clave privada asociada a este certificado para la exportación. Tendrá que solicitar de nuevo el certificado y, antes de que se inicie la exportación, deberá asegurarse de que el certificado está marcado para que se exporte la clave privada. Póngase en contacto con el administrador o proveedor de entidades de certificación.



9.  En el cuadro de diálogo Export File Formats, seleccione **Intercambio de información personal: PKCS\#12 (.PFX)** y, a continuación, seleccione lo siguiente:
    
      - Si es posible, incluir todos los certificados en la ruta de acceso de certificación
    
      - Exportar todas las propiedades extendidas
        
        > [!WARNING]  
        > Cuando exporte el certificado desde un servidor perimetral, no seleccione <strong>Eliminar la clave privada si la exportación es correcta</strong> . Al seleccionar esta opción es necesario importar el certificado y la clave privada a este servidor perimetral.
        


10. Después, haga clic en **Siguiente**.

11. Escriba una contraseña para la clave privada, vuelva a escribirla para confirmarla y, entonces, haga clic en **Siguiente**.

12. Escriba la ruta y nombre de archivo del certificado exportado, utilizando la extensión de archivo .pfx. La ruta debe estar accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte mediante medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente** .

13. Revise el resumen en **Finalización del Asistente para exportación de certificados** y, a continuación, haga clic en **Finalizar**.

14. En el cuadro de diálogo que indica que la exportación se ha completado correctamente, haga clic en **Aceptar**.

15. Importe el archivo de certificado exportado en los demás servidores perimetrales siguiendo los pasos descritos en el procedimiento “Para importar el certificado para la interfaz externa del servidor perimetral”, que encontrará más arriba en este tema.

## Para asignar el certificado para la interfaz externa del servidor perimetral

1.  En cada servidor perimetral, en el Asistente para la implementación, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

2.  En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.

3.  En la página **Asignación del certificado**, haga clic en **Certificado perimetral externo** y active la casilla **Usos avanzados de certificados**.

4.  En la página **Usos avanzados de certificados**, active todas las casillas para asignar el certificado para todos los usos.

5.  En la página **Almacén de certificado**, seleccione el certificado público que solicitó e importó para la interfaz externa del servidor perimetral.
    

    > [!NOTE]
    > Si el certificado que solicitó e importó no está en la lista, uno de los métodos para solucionar el problema consiste en comprobar que el nombre de sujeto y los nombres alternativos de sujeto del certificado cumplen todos los requisitos para el certificado y, si importó manualmente el certificado y la cadena de certificados en lugar de usar los procedimientos anteriores, que el certificado se encuentre en el almacén de certificados correcto (el almacén de certificados del equipo, no el almacén de certificados del usuario o del servicio).



6.  En la página **Resumen de asignación de certificados**, revise su configuración y, a continuación, haga clic en **Siguiente** para asignar los certificados.

7.  En la página de finalización del asistente, haga clic en **Finalizar**.

8.  Después de usar este procedimiento para asignar el certificado perimetral, abra el complemento Certificado en cada servidor, expanda **Certificados (equipo local)** , expanda **Personal** , haga clic en **Certificados** y, finalmente, compruebe que el certificado aparezca en el panel de detalles.

9.  Si la implementación incluye varios servidores perimetrales, repita este procedimiento con todos los servidores perimetrales.

