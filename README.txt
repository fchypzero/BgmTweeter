Properer Bangumi RSS
v1.1a by fishswing <me@swingworks.net> 2013-07-07
http://www.swingworks.net

����Ŀ��feed����ģ��ʹ����feedcreator�⣨�汾1.8�������������һЩ�޸ģ�
�ÿ��ļ�����LGPLЭ�������Ȩ����Դ�������Ȩ�ı��ĸ���λ��feedcreatorĿ¼�¡�
����Ŀ������΢������ģ��ʹ��������΢������ƽ̨�Ĺٷ�PHP SDK�����������һЩ�޸ġ�
����Ŀ��Twitter����ģ��ʹ����abraham��twitteroauth�Ⲣ���������һЩ�޸ġ�
����Ŀץȡ�ʹ������Ϣ��Bangumi����ƻ�(bgm.tv)�ṩ����Ȩ�����ڸ��Եİ�Ȩ�����û���
��Ŀ������������MIT License������Ȩ������Ȩ�ı�λ�ڸ�Ŀ¼�µ�LICENSE.txt��

ʹ�ñ���Ŀ��������Ĭ������������Ӧ��Э�顣

--

����Ŀ��һ���Ľ����Bangumi RSS���������PHP 5������֧��curl���������С�
ĿǰBangumiԭ��RSS���ܵ�Ч���ܲ
���ø���Ŀ�������һ���ɶ��Ը��õ�RSS������ͬ����Twitter��΢�����罻�����ϡ�
Ŀǰ��Ŀ�Ѿ�����������΢����Twitter���Զ��������ܡ�

��ϸ����������
http://www.swingworks.net/2012/04/propbgmrss/

��Ŀ��ҳ��
http://code.google.com/p/propbgmrss/

--

v1.0b������v1.1a˵��
��getmyrss.php�Լ�twitter/twitteroauthĿ¼�µ������ļ����Ǽ��ɡ�

v1.0������v1.0b˵����
��getmyrss.php, weibo/sendweibo.php��twitter/sendtwitter.php�����ļ����Ǽ��ɡ�
�統ǰ���з��������������뽫������Ŀ¼�µ�titlecache.id�ļ�ɾ����������������档

--

ʹ��˵����

1. �޸�config.php����������Ϣ������$bgm_typeĿǰ��֧��progress(����)��subject(�ղ�)��

2. ����ʹ��΢����Twitter�������ܣ���ʹ��cron������ִ��index.php������������cron.php��
   ����index.php��url��Ȼ���ں�̨���ġ��ƻ����񡱻�ʱ���ػ��������½�һ��ָ����磺
   php /home/<username>/domains/<yourdomain>/public_html/propbgmrss/cron.php >/dev/null 2>&1
   �Ƽ���������Ƶ�ʵ�Ϊÿ5����(*/5)��ÿ10����(*/10)����һ��ʼ�������һЩ���������Ƿ���ȷ��
   �����config.php�а�$is_redirect��Ϊfalse��

3a.����Ҫʹ������΢���������ܣ��������ú�cron��Ȼ�����˴���һ��app������Ϊ��
1) ��΢������ƽ̨Ӧ�ÿ���ҳ(http://open.weibo.com/development)����һ������ҳӦ�á���
2) ����Ӧ�õ�ַ������Ϊ http://<yourdomain>/propbgmrss/weibo/��������������Ϣ���㡰��������
3) �紴���ɹ������ڡ��߼���Ϣ��������Ȩ�ص�ҳ���͡�ȡ����Ȩ�ص�ҳ������Ϊ
   http://<yourdomain>/propbgmrss/weibo/callback.php
   Ȼ���¼��App-Key��App-Secret���ر�ҳ�棻
4) ��weibo/config.php����App-Key��App-Secret�ͻص�ҳ��ַ(Callback URL)��
5) �ڸ�Ŀ¼��config.php�н�$weibo_enabled��Ϊtrue�������ú�$weibo_pattern��
6) ���κ�ʱ�򣨰�����󣩶�����app�ύ��ˣ�

3b.����Ҫʹ��Twitter�������ܣ��������ú�cron��Ȼ��Twitter����һ��app������Ϊ��
1) ��Twitter Developersҳ��(https://dev.twitter.com/)�����Create an app����
2) ����Callback URL������Ϊ http://<yourdomain>/propbgmrss/twitter/callback.php��
3) �紴���ɹ��������Applicationҳ�棬�����Settings��ѡ���
4) ����Application Type���еġ�Access��ѡ��Ϊ��Read and Write����Ȼ���ײ��ġ�Update����
5) �ص���Details��ѡ�����¼Consumer key��Consumer secret������twitter/config.php��
6) �ڸ�Ŀ¼��config.php�н�$twitter_enabled��Ϊtrue�������ú�$twitter_pattern��

4. ������propbgmrssĿ¼�ϴ���php��������
   ��������΢�����ܣ������ http://<yourdomain>/propbgmrss/weibo/ �����Ȩ��
   ��������Twitter���ܣ������ http://<yourdomain>/propbgmrss/twitter/ �����Ȩ��
   Ȼ�����һ�� http://<yourdomain>/propbgmrss/ �����Ƿ�ɹ�����rss��
   ��δ���ù�cron��rss��ַ�� http://<yourdomain>/propbgmrss/
   ����������cron����rss��ַ��Ϊ http://<yourdomain>/propbgmrss/rss.xml
   �Ժ�rss�Ķ���ָ�������ַ���ɡ�

5. ����feedcreator������ƣ��������Ҫͬʱ���ɶ��feed������Ⱥ��ղظ�һ������
   �뿽��index.php��config.phpΪindex2.php��config2.php��
   ��config.php��config2.php�и�����$rss_filename���ò�ͬ���ļ�����
   Ȼ���޸�index2.php��require_once("config.php")Ϊrequire_once("config2.php")��
   ���ʹ��cron�����轫index2.php��ӵ�cron.php�С�

--

������־��

2013-07-07 v1.1a
1.�������黰��Ϊ.5ʱ��ʾ��λ�����⡣

2013-07-06 v1.1
1.֧��Twitter API v1.1��

2013-04-30 v1.0b
1.����������������������⡣

2013-04-05 v1.0a
1.�����Զ��ضϹ��ܣ���ֹ��������140�����Ƶ��·���ʧ�ܡ�

2012-11-14 v1.0
1.�Ľ�����΢����Ȩҳ����ʾ��ʽ����ʾ��Ч�ڣ�
2.�����ܻ���Ϊ??�ķ�����ĳЩ����²��ܸ���feed�����⣻
3.��������SDK��һ��ȱ�ݵ���δ�����̱�ǩ�ķ������޷���Ȩ�����⡣

2012-09-03 v0.9
1.������Bangumi��վ΢����ɷ����������޷���ʾ�����⣻
2.����������΢��OAuth V2�˿ڣ�
3.�������΢��V2�˿ڵĻ��ƽ����Ż�������ԭ�û�������Ȩ����ʾ��Ч�ڣ�
4.������Ȩҳ��ʾ��ǰ����״̬��

2012-06-10 v0.8
1.����Twitter�Զ��������ܣ�
2.������oauth�ļ���飬�ļ��Ѵ���ʱ��ֹ��Ȩ�����Է�ֹ������ð�ã�
3.�޸�OAuth���������΢����ͻ���⣻
4.����������΢������pattern֧�ֵ��ֶΣ�
5.΢��������������ʾ��ʽ��
6.���뾫���Ż���

2012-06-02 v0.7
1.����������΢���Զ��������ܡ���Ϊʹ��oauth1��Ȩ����������Ȩһ�ξͿ��Գ��������ˡ�

2012-05-26 v0.5
1.�������ķ�������ʾ��

2012-04-10 v0.4
1.��������΢���Զ��������ܡ�

2012-04-03 v0.3
��һ�������汾
1.ȥ������ѭ����飻
2.�����鼮���Ȳ�����ʾ�����⣻
3.�������ȱ���������½ضϵ����⡣

2012-03-31 v0.2
���԰汾
