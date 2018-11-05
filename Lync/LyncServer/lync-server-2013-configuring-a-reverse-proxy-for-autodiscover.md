---
title: Configurar un proxy inverso para la detección automática
TOCTitle: Configurar un proxy inverso para la detección automática
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945619(v=OCS.15)
ms:contentKeyID: 52061607
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un proxy inverso para la detección automática

 

_**Última modificación del tema:** 2012-12-12_

La Detección automática y la compatibilidad con clientes que usan esta característica requieren la modificación de una regla de publicación web existente o la creación de una nueva para el proxy inverso. En cualquiera de los dos casos, esto es independiente de la decisión de actualizar o no las listas de nombres alternativos del sujeto de los certificados del proxy inverso.

Si decide usar HTTPS para solicitudes iniciales del servicio Detección automática de Lync Server 2013 y actualizar las listas de nombres alternativos del sujeto en los certificados del proxy inverso, debe asignar el certificado público actualizado a la escucha de Capa de sockets seguros (SSL) en su proxy inverso. La actualización necesaria al certificado (público) externo incluirá la entrada de nombre alternativo del sujeto (SAN) para lyncdiscover.\<nombre de dominio\>. Luego debe modificar la escucha existente de los servicios web externos o crear una nueva regla de publicación web para la dirección URL del servicio Detección automática externa, por ejemplo, **lyncdiscover.contoso.com**. Si aún no tiene una regla de publicación web para la dirección URL de los servicios web de Lync Server 2013 externa para el Grupo de servidores front-end y el Grupo de directores (si ha implementado Directores), también debe proporcionar una.


> [!NOTE]
> La escucha y la regla de publicación del proxy inverso pueden dar servicio a los servicios web externos y al servicio Detección automática, siempre que el certificado asignado a la escucha contenga el nombre de sujeto necesario y los nombres alternativos del sujeto para ambos. Para obtener detalles sobre la configuración predeterminada de la regla de publicación y la escucha web, vea <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de los servidores proxy inversos para Lync Server 2013</A>.



Si decide usar HTTP para las solicitudes del servicio Detección automática de manera que no tenga que actualizar los nombres alternativos del sujeto del proxy inverso, debe crear o modificar una regla de publicación web para el puerto 80.

Los procedimientos de esta sección describen cómo crear o modificar reglas de publicación web en Microsoft Forefront Threat Management Gateway 2010 para la detección automática.


> [!NOTE]
> Estos procedimientos asumen que ha instalado la edición Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si está usando otro proxy inverso, los procedimientos son similares, pero deberá consultar la documentación del producto de terceros.



## Para crear una regla de publicación web para la dirección URL externa de Detección automática

1.  Haga clic en **Inicio**, elija **Programas**, **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación web**, escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, LyncDiscoveryURL).

4.  En la página **Seleccionar acción de regla**, seleccione **Permitir**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectar al servidor web o conjunto de servidores publicado**.

7.  En la página **Detalles internos de publicación**, en **Nombre interno del sitio**, escriba el nombre de dominio completo (FQDN) del Grupo de directores (por ejemplo, lyncdir01.contoso.local). Si crea una regla para la dirección URL de servicios web externos en el Grupo de servidores front-end, escriba el FQDN del Grupo de servidores front-end (por ejemplo, lyncpool01.contoso.local).

8.  En la página **Detalles internos de publicación**, en **Ruta de acceso (opcional)**, escriba **/\*** para la ruta de la carpeta que se va a publicar y, a continuación, seleccione **Reenviar el encabezado de host original**.

9.  En la página **Detalles de nombre público**, siga este procedimiento:
    
      - En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.
    
      - En **Nombre público**, escriba **lyncdiscover.***\<dominiosip\>* (la dirección URL externa del servicio Detección automática). Si crea una regla para la dirección URL de servicios web externos en el Grupo de servidores front-end, escriba el FQDN de los servicios web externos en el Grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
      - En **Ruta de acceso**, escriba **/\***.

10. En la página **Seleccionar escucha web**, en **Escucha web**, seleccione su escucha SSL existente con el certificado público actualizado.

11. En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente se puede autenticar directamente**.

12. En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.

13. En la página **Finalización del Asistente para nueva regla de publicación web**, compruebe que la configuración de la regla de publicación web sea correcta y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.

15. En la pestaña **Para**, realice el siguiente procedimiento:
    
      - Seleccione **Reenviar el encabezado de host original en lugar del real**.
    
      - Seleccione **Las peticiones parecen provenir del equipo de Forefront TMG**.

16. En la pestaña **Protocolo de puente**, configure lo siguiente:
    
      - Seleccione **Servidor web**.
    
      - Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.
    
      - Seleccione **Redirigir peticiones al puerto SSL** y escriba **4443** para el número de puerto.

17. Haga clic en **Aceptar**.

18. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

19. Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

## Para modificar una regla de publicación web existente para agregar la dirección URL y el SAN de Detección automática externos

1.  Haga clic en **Inicio**, elija **Programas**, **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.
    
    > [!IMPORTANT]  
    > Repetirá la modificación para cada regla de publicación y escucha que tenga. Normalmente, será una regla y escucha para el Grupos de servidores front-end y una para los grupos de Directores o Director opcionales, si los ha implementado.
    


2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall** y haga clic en la regla aplicable. En la pestaña **Tareas**, haga clic en **Editar regla seleccionada**.

3.  En la pestaña **Nombre público**, en **Esta regla se aplica a**, seleccione **Peticiones para los sitios web siguientes**.

4.  Haga clic en **Agregar**, escriba el nombre del nuevo sitio de Detección automática (por ejemplo, “lyncdiscover.contoso.com”) y, a continuación, haga clic en **Aceptar**.

5.  En la pestaña **Escucha**, haga clic en **Seleccionar certificado** y asigne el nuevo certificado con las entradas SAN de Detección automática agregadas. Cierre las propiedades de escucha y publicación web.

6.  Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

7.  Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

## Para crear una regla de publicación web para el puerto 80

1.  Haga clic en **Inicio**, elija **Programas**, **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación web**, escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, Detección automática de Lync (HTTP)).

4.  En la página **Seleccionar acción de regla**, seleccione **Permitir**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar conexiones no seguras para conectar al servidor web o conjunto de servidores publicado**.

7.  En la página **Detalles internos de publicación**, en **Nombre interno del sitio**, escriba el FQDN de servicios web internos para su Grupo de servidores front-end (por ejemplo, lyncpool01.contoso.local).

8.  En la página **Detalles internos de publicación**, en **Ruta de acceso (opcional)**, escriba **/\*** como la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **Reenviar el encabezado de host original en lugar del especificado en el campo del nombre de sitio interno**.

9.  En la página **Detalles de nombre público**, siga este procedimiento:
    
      - En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.
    
      - En **Nombre público**, escriba **lyncdiscover.***\<dominiosip\>* (la dirección URL externa del servicio Detección automática).
    
      - En **Ruta de acceso**, escriba **/\***.

10. En la página **Seleccionar escucha web**, en **Escucha web**, seleccione una escucha web o use el Asistente para nueva definición de escucha web para crear una nueva.

11. En la página **Delegación de autenticación**, seleccione **Sin delegación, y el cliente no se puede autenticar directamente**.

12. En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.

13. En la página **Finalización del Asistente para nueva regla de publicación web**, compruebe que la configuración de la regla de publicación web sea correcta y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.

15. En la pestaña **Protocolo de puente**, configure lo siguiente:
    
      - Seleccione **Servidor web**.
    
      - Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.
    
      - Compruebe que **Redirigir peticiones al puerto SSL** no esté seleccionado.

16. Haga clic en **Aceptar**.

17. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

18. Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

19. Compruebe que la dirección URL externa del servicio Detección automática no esté definida en otra regla de publicación web.

## Vea también

#### Conceptos

[Configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)

