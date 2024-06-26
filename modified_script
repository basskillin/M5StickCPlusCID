<?php
class Send_to_URL extends superfecta_base {

    public $description = "This source will send the CID number and the CID name to an URL for external processing. The URL you enter will be sent with the actual values substituted for [NAME] and [NUMBER] but otherwise UNMODIFIED.";
    public $version_requirement = "2.11";
    public $source_param = array(
        'URL_address' => array(
            'description' => 'Specify a URL to send CID/CNAM data to. Use the format \'http://url.org?thenumber=[NUMBER]&CLID=[NAME]\' where [NAME] and [NUMBER] will have actual values substituted',
            'type' => 'textarea',
            'default' => "http://10.0.0.10:80/?thenumber=[NUMBER]&CLID=[NAME]"
        )
    );

    function post_processing($cache_found, $winning_source, $first_caller_id, $run_param, $thenumber) {
        if (($run_param['URL_address'] != '') && ($first_caller_id != '')) {
            // replace [NAME] and [NUMBER] placeholders with actual urlencoded values
            $url = $run_param['URL_address'];
            $url = str_replace('[NAME]',  urlencode($first_caller_id), $url);
            $url = str_replace('[NUMBER]', urlencode($thenumber), $url);
            $url = str_replace('[name]',  urlencode($first_caller_id), $url);
            $url = str_replace('[number]', urlencode($thenumber), $url);
            $this->DebugPrint("Send to URL: {$url}");

            $value = $this->get_url_contents($url);
        }
    }
}
?>
