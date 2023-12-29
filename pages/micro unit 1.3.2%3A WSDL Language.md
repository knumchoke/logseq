- ```php
  <?php
    $client = new SoapClient(NULL,
                            array(
                            "location" => "http://64.124.140.30:9090/soap",
                            "uri" => "urn:xmethod-delayed-qoutes",
                            "style" => SOAP_PRC,
                            "use" => SOAP_ENCODED
                            ));
    print($client->__call(
    /* SOAP Method Name*/
    "getQoute",
    ))
    ?>
  ```