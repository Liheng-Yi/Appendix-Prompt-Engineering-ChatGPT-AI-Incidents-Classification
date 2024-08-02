## G-Prompt

This appendix contains the different prompts for calculating the tokens used

# Zeroshot
```"""
        Imagine a computer researcher trying to categorize a list of incidents of irresponsible use of artificial intelligence technology.    
        Given the aggregated news article texts on relevant incidents, please extract the following information, your responses should be well thought-out and well-supported by the content of the articles, please also follow instructions of this prompt.
        1. Fill out the following fields:
        - Country (output "Worldwide" if the incident happened across multiple countries):
        - State (if not applicable leave blank):
        - City (if not applicable leave blank):
        - Continent (output "Worldwide" if the incident happened across multiple countries):
        - Company (i.e. the company that developed the technology involved in this incident):
        - Company city (the city where the headquarters of this company is located. If the company recently moved headquarters, please use the location of the new headquarter):
        - Company state (the state of the company city, if applicable, if not leave blank):
        - Affected population (let's think about who are the affected demographic and which people are affected, it need not necessarily be from this list): 
        - Number of people actually affected (let's check the number of people directly affected according to the article. Give a total number. If unknown output 'Unknown'):
        - Number of people potentially affected (let's check the article text to see if this information is provided or suggested, if not you may ouput 'Unknown'):
        - Classes of irresponsible AI use (please follow the rules and refer to this taxonomy: 
                {taxa.classes}    
        Rule1: There could be more than one classes the article classifies as. 
        Rule2: DO NOT create your own class, adhere strictly to the provided list.
        - Subclasses (please follow the rules and refer to this taxonomy structure: 
                 {taxa.subclasses}
        Rule1 : The subclasses should be the children of the classes. Let's think about which sub-categories of the class/classes this article belong in. 
        Rule2: DO NOT ADD subclass fields that are NOT in the provided taxonomy list
        Rule3: If there is no subclass for a particular class in the taxonomy, leave it.
                - Sub-subclass (please follow the rules and refer to this taxonomy structure: 
               {taxa.sub_subclasses}
        , the taxonony is defined as such: {taxa.structure}. 
        Rule1: Only find the sub-subclass relation in the provided taxonomy. 
        Rule2: DO NOT ADD OR CREATE sub-subclass fields that are not in the provided taxonomy list. 
        Rule3: If a subclass in the taxonomy does not have a sub-subclass, leave it.
        Rule4: If none of the subclasses have sub-subclasses, just leave the field empty e.g. sub-subclass:[]
        - Area of AI Application:
        - Online (yes or no):

        Article Content:
        ================== Start of Article Content =================
        {article_text}
        ================== End of Article Content ===================
        """
```