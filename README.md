cmimapper
=========

Python module to convert scorm.com JSON interaction to CMI format

What this modules does ?
=======================

This module takes i/p a JSON file and gives o/p as a JSON with key replaced by cmi prefix according to SCORM standards.
Currently with scorm.com API, interactions reports are generated in XML format. By using xmltodict (another python mod.)
reports can be converted to JSON but the generated JSON is a nested dictionary which doesn't have any cmi prefix.
Hence this module takes care of this problem. It generates a simple python dictionary with cmi prefix which can be used 
to compare reports.

Sample XML from Scorm Cloud
===========================

 <interaction id="4160_Type_the_question_here">
                <type>TrueFalse</type>
                <objectives>
                  <objective id="Quiz_20137812216"/>
                </objectives>
                <timestamp>2013-07-11T13:55:16</timestamp>
                <correct_responses>
                  <response id="t"/>
                </correct_responses>
                <weighting>10.0</weighting>
                <learner_response>t</learner_response>
                <result>correct</result>
                <latency>0000:00:06.58</latency>
                <description/>

Sample JSON
===========
{             "@id": "4160_Type_the_question_here", 
              "correct_responses": {
                        "response": {
                              "@id": "t"
                                    }
                                    }, 
                                        
CMI JSON
========
"cmi.interactions.1.correct_responses.0.pattern": "t", 
    "cmi.interactions.1.description": null, 
    "cmi.interactions.1.id": "4160_Type_the_question_here", 
    "cmi.interactions.1.learner_response": "t", 
    "cmi.interactions.1.objectives.0.id": "Quiz_20137812216", 
    "cmi.interactions.1.result": "correct", 
    "cmi.interactions.1.type": "TrueFalse", 
    "cmi.interactions.1.weighting:": "10.0", 
    
    
How to use this module
======================

For windows: c:\>  python setup.py install
    
    
    
    
