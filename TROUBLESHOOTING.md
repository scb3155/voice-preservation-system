# Troubleshooting Guide

## Common Issues & Solutions for Shane Battier Writing System

### 🔧 System Access Issues

#### Problem: Can't Access GitHub Voice Files
**Symptoms**: Error loading voice patterns, system can't find repository
**Solutions**:
1. **Check Repository URL**: Ensure https://github.com/scb3155/shane-writing-system is accessible
2. **Use Raw File URLs**: Access files directly via https://raw.githubusercontent.com/scb3155/shane-writing-system/main/shane-voice-preservation/[filename].txt
3. **Manual Loading**: Copy/paste voice file contents directly into prompts
4. **Repository Status**: Verify repository is public or you have access

#### Problem: Voice Files Not Loading Properly
**Symptoms**: Low voice match scores, generic output, missing authentic elements
**Solutions**:
1. **File Format Check**: Ensure all voice files are .txt format
2. **Content Verification**: Confirm files contain actual Shane writing samples
3. **File Size**: Check files aren't empty or corrupted
4. **Manual Verification**: Read one file directly to confirm content quality

#### Problem: Cross-Device Access Issues
**Symptoms**: System works on one device but not others
**Solutions**:
1. **Use GitHub URLs**: Always reference repository URLs, not local files
2. **Clear Browser Cache**: If using web interface, clear cache and cookies
3. **Network Access**: Ensure device can access GitHub.com
4. **Command Consistency**: Use exact same commands across all devices

### 📝 Content Generation Issues

#### Problem: Low Voice Match Scores (Below 90%)
**Symptoms**: Content doesn't sound like Shane, too formal or corporate
**Solutions**:
1. **Check Voice Files**: Ensure GitHub files contain authentic Shane samples
2. **Add More Samples**: Include more diverse voice examples in repository
3. **Specify Voice Elements**: Explicitly mention Shane's patterns in prompts
4. **Manual Review**: Compare output against known authentic Shane content

#### Problem: Content Too Formal/Corporate
**Symptoms**: Business jargon, formal language, missing personality
**Solutions**:
1. **Reload Voice Files**: Re-run voice loading command
2. **Add Anti-Patterns**: Specify corporate language to avoid
3. **Emphasize Authenticity**: Request specific Shane voice elements
4. **Use Voice Strict Mode**: Run `/voice_strict` for enhanced validation

#### Problem: Missing Shane's Personality Elements
**Symptoms**: No parenthetical thoughts, missing humor, too serious
**Solutions**:
1. **Update Voice Files**: Add more examples of Shane's humor and style
2. **Specify Elements**: Request specific personality traits in prompts
3. **Reference Examples**: Include actual Shane phrases in voice files
4. **Iterative Refinement**: Use `/voice_match_check` to improve content

### 🔄 Export & Integration Issues

#### Problem: Airtable Export Failing
**Symptoms**: Content generated but not appearing in Airtable
**Solutions**:
1. **Check API Keys**: Verify Airtable API key and Base ID are correct
2. **Manual Entry**: Copy content manually into Airtable as backup
3. **Field Mapping**: Ensure Airtable fields match system expectations
4. **Permission Check**: Verify API has write access to base

#### Problem: Google Drive Integration Issues
**Symptoms**: Documents not created or folders missing
**Solutions**:
1. **Check Permissions**: Ensure Google Drive API access enabled
2. **Manual Folder Creation**: Create folder structure manually
3. **Document Templates**: Use provided templates for consistent formatting
4. **Sharing Settings**: Verify folder sharing permissions

#### Problem: Content Formatting Issues in Export
**Symptoms**: Poor formatting, missing sections, garbled text
**Solutions**:
1. **Use Templates**: Apply provided formatting templates
2. **Manual Formatting**: Copy content and format manually
3. **Platform Limits**: Check character/word limits for each platform
4. **Preview Content**: Review before final export

### 💻 Cross-Platform Workflow Issues

#### Problem: Session State Lost Between Devices
**Symptoms**: Have to restart setup on each device
**Solutions**:
1. **Use Cloud Storage**: Store session state in Airtable/Google
2. **Bookmark Commands**: Save frequently used commands
3. **Standard Workflow**: Follow consistent startup routine
4. **GitHub Reference**: Always start with voice file loading

#### Problem: Inconsistent Voice Across Devices
**Symptoms**: Content sounds different depending on device used
**Solutions**:
1. **Same Voice Files**: Ensure same GitHub repository accessed
2. **Identical Commands**: Use exact same prompts across devices
3. **Voice Validation**: Run voice check on each device
4. **Reference Consistency**: Load same voice patterns each time

#### Problem: Content Not Syncing Between Platforms
**Symptoms**: Content in one platform but not others
**Solutions**:
1. **Export Verification**: Confirm export completed successfully
2. **Platform Status**: Check each platform's sync status
3. **Manual Sync**: Copy content manually if automatic sync fails
4. **Backup Workflow**: Use multiple export methods

### 🎯 Performance & Quality Issues

#### Problem: Content Lacks Engagement
**Symptoms**: Low response rates, poor audience connection
**Solutions**:
1. **Voice Authenticity**: Increase voice match scores to 95%+
2. **Emotional Honesty**: Add more vulnerable content to voice files
3. **Story Elements**: Include more personal stories in content
4. **Platform Optimization**: Adjust format for each platform's audience

#### Problem: Taking Too Long to Generate Content
**Symptoms**: Slow processing, multiple iterations needed
**Solutions**:
1. **Clear Instructions**: Use specific, detailed prompts
2. **Good Input**: Provide quality raw content with clear direction
3. **Voice Files Quality**: Ensure voice samples are comprehensive
4. **Streamlined Process**: Use `/all_formats` for complete packages

#### Problem: Content Repetitive or Generic
**Symptoms**: Similar content repeatedly, lack of variety
**Solutions**:
1. **Diverse Voice Samples**: Add varied examples to GitHub repository
2. **Different Content Types**: Mix stories, insights, tutorials
3. **Fresh Input**: Use varied raw content sources
4. **Voice File Updates**: Regularly add new authentic samples

### 🚨 Emergency Workflows

#### If GitHub Access Completely Lost
**Backup Plan**:
1. **Local Voice Files**: Keep backup copies of voice samples
2. **Manual Voice Loading**: Copy/paste voice patterns into prompts
3. **Alternative Repository**: Set up backup GitHub account
4. **Platform Direct**: Work directly in editing platforms

#### If AI System Not Working
**Manual Process**:
1. **Use Voice Templates**: Apply Shane's patterns manually
2. **Reference Samples**: Compare against authentic Shane content
3. **Platform Native**: Work directly in each platform's interface
4. **Voice Validation**: Manual authenticity checking

#### If Export Systems Down
**Content Backup**:
1. **Local Storage**: Save content locally as backup
2. **Email Draft**: Send content to email for access anywhere
3. **Cloud Notes**: Use any available note-taking app
4. **Manual Publishing**: Post directly to platforms

### 📊 Optimization Tips

#### Improving Voice Match Scores
1. **More Authentic Samples**: Add diverse Shane writing to GitHub
2. **Better Input Quality**: Provide clearer raw content
3. **Specific Requests**: Ask for particular Shane voice elements
4. **Iterative Improvement**: Use feedback to refine system

#### Streamlining Workflow
1. **Standard Commands**: Create shortcuts for frequent operations
2. **Batch Processing**: Generate multiple pieces in one session
3. **Template Usage**: Apply consistent formatting templates
4. **Performance Tracking**: Monitor what works best

#### Maintaining Quality
1. **Regular Voice Updates**: Add new authentic samples monthly
2. **Performance Analysis**: Track engagement and adjust
3. **System Testing**: Regular checks with known good content
4. **Continuous Learning**: Evolve system based on results

### 📞 Getting Help

#### Self-Diagnosis Checklist
- [ ] GitHub repository accessible?
- [ ] Voice files loading properly?
- [ ] Commands copied exactly?
- [ ] Export platforms configured?
- [ ] Voice match scores above 90%?

#### Quick Fixes
1. **Restart Process**: Clear session and reload voice files
2. **Check URLs**: Verify all GitHub links are working
3. **Manual Override**: Use backup manual processes
4. **Simple Test**: Try with known working content

#### System Health Check
Run this diagnostic command monthly:
```
Test Shane's voice system:

1. Load voice files from GitHub repository
2. Process simple test content: "This is a test of my voice system"
3. Generate short output for each platform
4. Check voice match scores (should be 90%+)
5. Verify export to chosen platform works
6. Report system status and any issues

Expected result: All systems operational, voice authenticity preserved.
```

Remember: The system is designed to be resilient. If one component fails, there are always backup methods to maintain your authentic voice and content creation workflow.