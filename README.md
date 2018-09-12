# Requirements Editor

A requirements editor is at the core of the Peak Shift DAO — it is meant to bridge between both non-technical and technical collaborators of a project.

Work requirements sent to the Peak Shift DAO need to be written in a specific format called Gherkin — gherkin was designed to reduce ambiguity in the requirements definitions.

```gherkin
@backend @python
Feature: Requirements Editor Backend

    @ipfs
    Scenario: Store on IPFS

    @ipfs
    Scenario: Retrieve from IPFS
        When a "GET" request is made to "/requirements/AmZtmD2..."
        Then a file containing the following is returned
        """
        {"msg": "available on ipfs"}
        """
```

```gherkin
@client @browser @ui
Feature: Requirements Editor UI
	- Requirements will be autosaved.

    Scenario: Create a new Requirement
        Given I am on "/"
        When I click "New Feature"
        Then I am on "/feature/new"
        And I see a textarea named "editor"
        And it is prefilled with
        """
        Feature: Your feature name
        As a ___
        I want to ___
        So that ___

        Scenario: ___
        Given ___
        When ___
        Then ___
        """
    Scenario: Autosave requirement locally
    Scenario: Edit Requirement
    Scenario: Gherkin is invalid
    Scenario: Gherkin is valid

@client @browser @localstorage
Feature: Editor Backup
    Scenario: Load from localstorage
    Scenario: Create periodic backup
        Given the "editor" field contains
        """
        a
        """
        When it changes to
        """
        ab
        """
        Then "feature__gherkin-editor" key in localstorage is
        """
        ab
        """
    Scenario: Autosave to localstorage onchange
        Given the "editor" field contains
        """
        a
        """
        When it changes to
        """
        ab
        """
        Then "feature__gherkin-editor" key in localstorage is
        """
        ab
        """
```

### Supplements

##### What is Gherkin?

Gherkin is a way to describe the functionality of a system by using Given, When, Then statements — it was designed to be non-technical and human readable.

##### Usability

###### Syntax Highlighter

Syntax highlighing can be used to imrpvoe readability of scenarios.

##### IPFS Primer

- https://flyingzumwalt.gitbooks.io/decentralized-web-primer/content/files-on-ipfs/lessons/add-and-retrieve-file-content.html
- https://medium.com/@JohnZettler/how-to-save-a-file-on-ipfs-a-7-step-primer-3476469536c7